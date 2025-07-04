# 🌐 How to Write Basic API Views Using `@api_view` and `Response` (Beginner-Friendly Guide)

When building an API with Django REST Framework (DRF), you write **views** to handle requests and send responses.  
Here’s **what API views are, and how to write a simple one step by step.**

---

## ❓ What is an API View?

✅ An **API view** is a Python function (or class) that decides what happens when someone sends a request to your API.  
For example:
- A GET request asks for a list of products.
- Your view gets the data, converts it to JSON, and sends it back.

✅ `@api_view` is a decorator from DRF that lets you write **function-based API views**.  
✅ `Response` is a helper that formats your data as JSON and sends it back.

---

## 🔷 How to Write a Basic API View

### ✅ Step 1: Import Tools

Open your app’s `views.py` and import:

```python
from rest_framework.decorators import api_view
from rest_framework.response import Response
from .models import Product
from .serializers import ProductSerializer
```

---

### ✅ Step 2: Write the View

Here’s a simple example:

```python
@api_view(['GET'])
def get_products(request):
    products = Product.objects.all()
    serializer = ProductSerializer(products, many=True)
    return Response(serializer.data)
```

---

## 🔷 What Does This Code Do?

✅ Step by step:
1️⃣ `@api_view(['GET'])` → This view responds to GET requests.  
2️⃣ `products = Product.objects.all()` → Fetch all products from the database.  
3️⃣ `serializer = ProductSerializer(products, many=True)` → Convert products to JSON.  
4️⃣ `return Response(serializer.data)` → Send the JSON data as the response.

---

### 🔷 Example Output

If your database has two products:

| id  | name      | price   |
|-----|-----------|---------|
| 1   | T-Shirt   | 19.99   |
| 2   | Shoes     | 49.99   |

The API will return:

```json
[
  { "id": 1, "name": "T-Shirt", "price": "19.99" },
  { "id": 2, "name": "Shoes", "price": "49.99" }
]
```

---

## 🏁 Summary: What & How

✅ **What is it?**
- An API view handles a request and returns JSON data.
- `@api_view` makes it easy to write function-based API views.
- `Response` sends the data back in JSON.

✅ **How to write it?**
1. Import `@api_view` and `Response`.
2. Query your data.
3. Serialize it.
4. Return it using `Response`.

🎉 That’s it — your API view is ready to serve data!

🔗 Learn more: [https://www.django-rest-framework.org/tutorial/quickstart/](https://www.django-rest-framework.org/tutorial/quickstart/)
