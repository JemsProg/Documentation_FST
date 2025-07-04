# 🔗 How to Install Django REST Framework (DRF) (Beginner-Friendly Guide)

If you want to build APIs in Django, you’ll need **Django REST Framework (DRF)**.  
Here’s **what DRF is, and how to install it step by step.**

---

## ❓ What is DRF?

✅ **Django REST Framework (DRF)** is a powerful toolkit for building **APIs** with Django.  
An API lets your backend send and receive data (like JSON) to/from your frontend or other apps.

For example:
- A React app fetching data from Django
- A mobile app connecting to your Django backend

Without DRF, building APIs in Django is more complicated.

---

## 🔷 How to Install DRF

### ✅ Step 1: Open Your Terminal

Make sure you’re in your Django project folder, or anywhere you can access Python.

---

### ✅ Step 2: Run the Install Command

In your terminal, type:

```bash
pip install djangorestframework
```

✅ This downloads and installs DRF into your environment.

You should see something like:
```
Successfully installed djangorestframework-x.x.x
```

---

### ✅ Step 3: Verify Installation

Optional: You can check that it installed by running:

```bash
pip show djangorestframework
```

You’ll see details about the package.

---

### ✅ Step 4: Register DRF in Your Project

After installing DRF, you must add it to your project’s `INSTALLED_APPS`.  

Open 📄 `backend/backend/settings.py` and add `'rest_framework'`:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',  # 👈 Add this line
]
```

Save the file.

---

## 🏁 Summary: What & How

✅ **What is it?**
- Django REST Framework is a library to help you build APIs easily in Django.

✅ **How to install?**
1. Run: `pip install djangorestframework`
2. Add `'rest_framework'` to `INSTALLED_APPS` in `settings.py`.

🎉 That’s it — you’re ready to start building APIs with Django!

🔗 Learn more: [https://www.django-rest-framework.org/](https://www.django-rest-framework.org/)
