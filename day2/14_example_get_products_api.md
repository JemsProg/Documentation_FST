# 🌐 Example: Simple `GET` API View (Beginner-Friendly Guide)

Here’s a super simple example of a Django REST Framework API view that lists all products as JSON.

---

## ✅ The Code

This code goes inside your app’s `views.py` file:

```python
from rest_framework.decorators import api_view
from rest_framework.response import Response
from .models import Product
from .serializers import ProductSerializer

@api_view(['GET'])
def get_products(request):
    products = Product.objects.all()
    serializer = ProductSerializer(products, many=True)
    return Response(serializer.data)
```

---

## 🔷 What It Does

✅ Step-by-step explanation:
1️⃣ `@api_view(['GET'])` → This view only responds to `GET` requests.  
2️⃣ `products = Product.objects.all()` → Fetch all product records from the database.  
3️⃣ `serializer = ProductSerializer(products, many=True)` → Convert all products into JSON-friendly format.  
4️⃣ `return Response(serializer.data)` → Send the serialized data back as a JSON response.

---

## 🔷 Example Output

If you visit this API endpoint in your browser or Postman, you’ll see something like this:

```json
[
  {
    "id": 1,
    "name": "T-Shirt",
    "price": "19.99"
  },
  {
    "id": 2,
    "name": "Shoes",
    "price": "49.99"
  }
]
```

---

## 🧩 Where to Use

You can connect this view to a URL in your `urls.py` like this:

```python
from django.urls import path
from .views import get_products

urlpatterns = [
    path('products/', get_products, name='get_products'),
]
```

Then visit: 🌐 [http://127.0.0.1:8000/products/](http://127.0.0.1:8000/products/)  

---

## 🏁 Summary

✅ This simple view does:  
- Accepts a `GET` request.
- Queries all products from the database.
- Serializes them into JSON.
- Returns the data in a clean API response.

🎉 That’s it — your first working API endpoint!

🔗 Learn more: [https://www.django-rest-framework.org/](https://www.django-rest-framework.org/)
