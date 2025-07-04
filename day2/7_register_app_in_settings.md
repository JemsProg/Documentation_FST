# 📝 How to Register an App in `settings.py` (Beginner-Friendly Guide)

After you create a Django app, you need to tell Django about it.  
Here’s **what it means to register your app, and how to do it step by step.**

---

## ❓ What Does “Register an App” Mean?

✅ When you create an app (like `base`), Django doesn’t automatically know to use it.  
You have to **register the app in your project’s settings file** so Django includes it when running the server.

Without registering, your app won’t work properly — models, views, and other features won’t be recognized.

---

## 🔷 How to Register an App

### ✅ Step 1: Open `settings.py`

Go to your Django project folder and open:  
📄 `backend/backend/settings.py`

---

### ✅ Step 2: Find the `INSTALLED_APPS` List

Inside `settings.py`, find the section that looks like this:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```

This is a list of all apps Django knows about.

---

### ✅ Step 3: Add Your App Name

If your app is named `base`, add it as a string at the end of the list:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'base',  # 👈 Add your app here
]
```

Save the file.

---

## 🏁 Summary: What & How

✅ **What does it mean?**  
- Registering your app tells Django to include it when running the project.

✅ **How to do it?**
1. Open `settings.py`
2. Find `INSTALLED_APPS`
3. Add your app name as a string (e.g., `'base'`)

🎉 That’s it — your app is now active and ready to use in your Django project!

🔗 Learn more: [https://docs.djangoproject.com/en/stable/ref/settings/#installed-apps](https://docs.djangoproject.com/en/stable/ref/settings/#installed-apps)
