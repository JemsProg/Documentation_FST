# 🌐 Setup URL Routing in Django (Beginner-Friendly Guide)

When building a web app or API with Django, you need to define **which URL runs which view**.  
This is called **URL routing** — and here’s what it is and how to set it up, step by step!

---

## ❓ What is URL Routing?

✅ URL routing is Django’s way of connecting **a URL in the browser** (like `/products/`) to **a Python view function** that sends a response.

Without URL routing, Django wouldn’t know what to do when someone visits a certain URL.

---

## 🔷 How to Set Up URL Routing

Here’s how you can set up routing for your app’s API endpoints:

---

## ✅ Step 1: Create or Open `urls.py` in Your App

Inside your app folder (e.g., `core/`), create a file called:

📄 `core/urls.py`

If it already exists, just open it.

---

## ✅ Step 2: Import Tools and Views

At the top of `core/urls.py`, write:

```python
from django.urls import path
from .views import get_products  # import your view
```

---

## ✅ Step 3: Define URL Patterns

Below the imports, add:

```python
urlpatterns = [
    path('products/', get_products, name='get_products'),
]
```

✅ This means:
- When someone visits `/products/`, Django calls the `get_products` view.

---

## ✅ Step 4: Include App URLs in Project URLs

Now open the **project-level** `urls.py` (inside the inner `backend/` folder):

📄 `backend/urls.py`

It looks something like this:

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
]
```

Modify it to include your app’s URLs:

```python
urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('core.urls')),  # 👈 include your app’s urls
]
```

✅ This means:
- Any URL starting with `/api/` will now look for routes in `core/urls.py`.
- So `/api/products/` will work!

---

## 🏁 Summary: What & How

✅ **What is URL routing?**
- It’s the system that tells Django what to do when someone visits a certain URL.

✅ **How to set it up?**
1. Create `urls.py` in your app and define `urlpatterns`.
2. Map URLs to your view functions.
3. Include your app’s `urls.py` in the project-level `urls.py`.

🎉 That’s it — your URLs are now connected to your views!

🔗 Learn more: [https://docs.djangoproject.com/en/stable/topics/http/urls/](https://docs.djangoproject.com/en/stable/topics/http/urls/)
