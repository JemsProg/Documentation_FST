# PayMongo Integration with Django (GCash Payment + Webhook)

This document describes the step-by-step process of integrating **PayMongo** GCash payment in a Django backend project, and successfully handling **webhook events** to mark orders as paid and create order items automatically.

---

## ✅ 1. Installing Required Dependencies

Install the `requests` library (used to communicate with PayMongo’s API):

```bash
pip install requests
```

This package allows you to make secure HTTP POST requests to PayMongo’s server.

---

## ✅ 2. Django Models Used

### `PaymenMethod` (Stores payment info)

```python
class PaymenMethod(models.Model):
    payment_id = models.AutoField(primary_key=True)
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    total_price = models.DecimalField(max_digits=10, decimal_places=2)
    is_paid = models.BooleanField(default=False)
    paid_at = models.DateField(null=True, blank=True)
    paymongo_payment_id = models.CharField(max_length=255, null=True, blank=True)
    paymongo_status = models.CharField(max_length=255, null=True, blank=True)
```

### `OrderItem` (Represents a confirmed order)

```python
class OrderItem(models.Model):
    order_id = models.AutoField(primary_key=True)
    product = models.ForeignKey(Product, on_delete=models.SET_NULL, null=True)
    payment = models.ForeignKey(PaymenMethod, on_delete=models.SET_NULL, null=True)
    qty = models.IntegerField()
    price = models.DecimalField(max_digits=10, decimal_places=2)
```

### `ShippingAddress`

```python
class ShippingAddress(models.Model):
    shipping_id = models.AutoField(primary_key=True)
    payment = models.ForeignKey(PaymenMethod, on_delete=models.CASCADE)
    full_name = models.CharField(max_length=255)
    address = models.CharField(max_length=255)
    city = models.CharField(max_length=100)
    postal_code = models.CharField(max_length=20)
    country = models.CharField(max_length=100)
```

---

## ✅ 3. CheckoutSerializer

Handles and validates user input before creating the PayMongo payment:

```python
class CheckoutSerializer(serializers.Serializer):
    total_price = serializers.DecimalField(max_digits=10, decimal_places=2)
    full_name = serializers.CharField(max_length=255)
    address = serializers.CharField(max_length=255)
    city = serializers.CharField(max_length=100)
    postal_code = serializers.CharField(max_length=20)
    country = serializers.CharField(max_length=100)
    email = serializers.EmailField()
    mobile = serializers.CharField(max_length=15, required=False)
```

---

## ✅ 4. Add URLs

In your `urls.py` file, register these two views:

```python
# checkout and webhook routes
path("api/payments/create/", views.create_gcash_payment, name="create-gcash-payment"),
path("api/paymongo/webhook/", views.paymongo_webhook, name="paymongo-webhook"),
```

---

## ✅ 5. Full Payment API Logic (copy and paste ready)

### `create_gcash_payment` View

This is the main function that creates a payment link using PayMongo’s `/v1/links` endpoint:

```python
@api_view(['POST'])
@permission_classes([IsAuthenticated])
def create_gcash_payment(request):
    serializer = CheckoutSerializer(data=request.data)
    if serializer.is_valid():
        data = serializer.validated_data
        user = request.user

        # Base64 encode your secret key
        secret_key = "sk_test_6Wu2UUWNZkq1KqyjxjFNEzvZ"
        encoded_key = base64.b64encode(f"{secret_key}:".encode()).decode()

        headers = {
            "Authorization": f"Basic {encoded_key}",
            "Content-Type": "application/json"
        }

        payload = {
            "data": {
                "attributes": {
                    "amount": int(data["total_price"] * 100),  # centavos
                    "description": "Order Payment",
                    "remarks": "GCash only",
                    "redirect": {
                        "success": "http://localhost:3000/payment-success",
                        "failed": "http://localhost:3000/payment-failed"
                    },
                    "billing": {
                        "name": data["full_name"],
                        "email": data["email"],
                        "phone": data.get("mobile")
                    },
                    "payment_method_types": ["gcash"]
                }
            }
        }

        response = requests.post("https://api.paymongo.com/v1/links", headers=headers, json=payload)
        result = response.json()

        if "data" in result:
            checkout_url = result["data"]["attributes"]["checkout_url"]
            paymongo_id = result["data"]["id"]
            status_str = result["data"]["attributes"]["status"]

            # Save to PaymenMethod model
            payment = PaymenMethod.objects.create(
                user=user,
                total_price=data["total_price"],
                is_paid=False,
                paymongo_payment_id=paymongo_id,
                paymongo_status=status_str
            )

            # Save to ShippingAddress model
            ShippingAddress.objects.create(
                payment=payment,
                full_name=data["full_name"],
                address=data["address"],
                city=data["city"],
                postal_code=data["postal_code"],
                country=data["country"]
            )

            return Response({"checkout_url": checkout_url}, status=200)

        return Response({"error": result}, status=400)

    return Response(serializer.errors, status=400)
```

This endpoint handles:

- Creating a GCash-only payment link
- Saving payment status
- Creating shipping address record
- Returning the PayMongo checkout URL

---

## ✅ 6. Webhook View to Confirm Payment

When the user completes payment, PayMongo sends a POST request to your webhook URL:

```python
@csrf_exempt
@api_view(['POST'])
def paymongo_webhook(request):
    try:
        payload = json.loads(request.body)
        event_type = payload.get("data", {}).get("attributes", {}).get("type")

        if event_type == "link.payment.paid":
            paymongo_id = payload["data"]["attributes"]["data"]["id"]

            payment = PaymenMethod.objects.filter(paymongo_payment_id=paymongo_id).first()

            if payment and not payment.is_paid:
                payment.is_paid = True
                payment.paid_at = now().date()
                payment.paymongo_status = "paid"
                payment.save()

                cart_items = CartUser.objects.filter(user=payment.user)

                for item in cart_items:
                    OrderItem.objects.create(
                        product=item.product,
                        payment=payment,
                        qty=item.qty,
                        price=item.product.product_price
                    )

                cart_items.delete()

                return Response({"message": "Payment confirmed. Order items created."}, status=200)

        return Response({"message": "Webhook received. No action taken."}, status=200)

    except Exception as e:
        return Response({"error": str(e)}, status=400)
```

This does:

- Confirms the payment
- Marks the DB payment as `paid`
- Moves cart items into `OrderItem`
- Deletes the user's cart

Make sure this view has CSRF exempt since PayMongo will not send a CSRF token.

---

## ✅ 7. Registering the Webhook in PayMongo

### If dashboard is not working:

Use curl instead:

```bash
curl -X POST https://api.paymongo.com/v1/webhooks \
  -u sk_test_xxx: \
  -H "Content-Type: application/json" \
  -d '{
    "data": {
      "attributes": {
        "url": "http://147.93.107.162:8003/api/paymongo/webhook/",
        "events": ["link.payment.paid"]
      }
    }
  }'
```

> If you see `resource_exists`, your webhook is already active.

---

## ✅ 8. Manually Triggering the Webhook

### For Testing:

```bash
curl -X POST http://147.93.107.162:8003/api/paymongo/webhook/ \
  -H "Content-Type: application/json" \
  --data '{
    "data": {
      "id": "evt_test_success",
      "type": "event",
      "attributes": {
        "type": "link.payment.paid",
        "data": {
          "id": "link_XXXXXXX"
        }
      }
    }
  }'
```

- If successful: `"Payment confirmed. Order items created."`

---

## ✅ 9. Deployment Notes

- Open port `8003` on your firewall.
- Use `gunicorn` to run Django manually:

```bash
gunicorn backend.wsgi:application --bind 0.0.0.0:8003 --access-logfile gunicorn.log --error-logfile gunicorn-error.log --daemon
```

- Use `tail -f gunicorn.log` to monitor webhook activity.

---

## ✅ 10. Final Integration Flow

| Step | Action                                                         |
| ---- | -------------------------------------------------------------- |
| 1    | User submits checkout info                                     |
| 2    | Backend sends payment link request to PayMongo                 |
| 3    | PayMongo returns checkout URL                                  |
| 4    | User pays via GCash / Maya / etc.                              |
| 5    | PayMongo sends webhook to `/api/paymongo/webhook/`             |
| 6    | Backend marks payment paid + creates order items + clears cart |

---

## ✅ Summary

- `create_gcash_payment` creates a payment link and stores billing info.
- `paymongo_webhook` processes successful payments.
- Uses `requests`, `base64`, and Django REST Framework to securely connect to PayMongo.
- Even with `gcash`, user will see multiple payment methods on the checkout page.

You’re done! 🎉

