# 🌐 CORS Headers in Django (Beginner-Friendly Guide)

When building a Django backend with a separate frontend (like React or Vue), you might see **CORS errors** in your browser.  
This guide explains **what CORS is, and how to handle it in Django using `django-cors-headers`.**

---

## ❓ What is CORS?

✅ **CORS (Cross-Origin Resource Sharing)** is a browser security feature.  
It prevents frontend apps running on one domain (like `http://localhost:3000`) from accessing APIs running on another domain (like `http://127.0.0.1:8000`) unless the server explicitly allows it.

Without CORS configuration, you may see an error like:
```
Access to fetch at 'http://127.0.0.1:8000/api/' from origin 'http://localhost:3000' has been blocked by CORS policy.
```

---

## 🔷 How to Fix CORS in Django

The easiest way is to use the `django-cors-headers` package.

---

## 🚀 Steps to Set Up `django-cors-headers`

### ✅ Step 1: Install the Package

Run this command in your terminal:
```bash
pip install django-cors-headers
```

---

### ✅ Step 2: Add it to `INSTALLED_APPS`

In your Django `settings.py`, add `'corsheaders'` to `INSTALLED_APPS`:
```python
INSTALLED_APPS = [
    'corsheaders',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```

---

### ✅ Step 3: Add the Middleware

In `settings.py`, add the `CorsMiddleware` at the top of the `MIDDLEWARE` list:
```python
MIDDLEWARE = [
    'corsheaders.middleware.CorsMiddleware',
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    ...
]
```

---

### ✅ Step 4: Configure Allowed Origins

Also in `settings.py`, define which origins are allowed to access your API. Example:
```python
CORS_ALLOWED_ORIGINS = [
    "http://localhost:3000",
    "http://127.0.0.1:3000",
]
```

If you want to allow **all origins** (not recommended for production):
```python
CORS_ALLOW_ALL_ORIGINS = True
```

---

## 🏁 Summary

✅ **What is CORS?**
- A browser rule that blocks cross-origin requests unless allowed by the server.

✅ **How to fix it in Django?**
1. Install `django-cors-headers`
2. Add it to `INSTALLED_APPS`
3. Add `CorsMiddleware` to `MIDDLEWARE`
4. Set `CORS_ALLOWED_ORIGINS` in `settings.py`

🎉 Done — your Django backend can now serve requests from your frontend app without CORS errors!

🔗 Learn more: [https://pypi.org/project/django-cors-headers/](https://pypi.org/project/django-cors-headers/)
