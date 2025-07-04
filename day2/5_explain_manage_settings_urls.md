# 📄 Explain `manage.py`, `settings.py`, `urls.py` (Beginner-Friendly Guide)

When you create a Django project, you’ll see some important files: **`manage.py`**, **`settings.py`**, and **`urls.py`**.  
Here’s **what each one does, and how you use them.**

---

## 📝 `manage.py`

### ✅ What is it?
- A command-line utility that helps you interact with your Django project.

### 🔷 How to use it?
You run it from the terminal to:
- Start the development server
- Run migrations
- Create apps

### 📌 Example commands:
```bash
python manage.py runserver      # start the server
python manage.py migrate        # apply database changes
python manage.py startapp core  # create a new app
```

Think of `manage.py` as your main control panel.

---

## 📝 `settings.py`

### ✅ What is it?
- The configuration file for your Django project.

It’s located here: `backend/backend/settings.py`

### 🔷 How to use it?
You edit `settings.py` to change things like:
- Installed apps
- Database settings
- Time zone & language
- Debug mode

📌 Example:
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'core',  # your app
]
```

Whenever you need to adjust how your project works, you’ll usually edit `settings.py`.

---

## 📝 `urls.py`

### ✅ What is it?
- The file where you define your URL routes.

It’s located here: `backend/backend/urls.py`

### 🔷 How to use it?
You edit `urls.py` to connect URLs to view functions.

📌 Example:
```python
from django.contrib import admin
from django.urls import path

urlpatterns = [
    path('admin/', admin.site.urls),
]
```

When someone visits `/admin/` in the browser, Django shows the admin page.

You can also include your app’s URLs here.

---

## 🏁 Summary: What & How

| File          | What it is                           | How you use it                      |
|----------------|-------------------------------------|-------------------------------------|
| `manage.py`   | Command-line tool for project tasks | Run server, migrations, create apps |
| `settings.py` | Project configuration file          | Edit settings like apps & database  |
| `urls.py`     | URL routing file                    | Map URLs to views                    |

🎉 That’s it — you now know what these files are for and how to use them!

🔗 Learn more: [https://docs.djangoproject.com/en/stable/intro/tutorial01/](https://docs.djangoproject.com/en/stable/intro/tutorial01/)
