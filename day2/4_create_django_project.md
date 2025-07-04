# 🌐 How to Create a Django Project (Beginner-Friendly Guide)

Once you’ve installed Django, the next step is to create your first Django project.  
Here’s **what it means, and how to do it step by step.**

---

## ❓ What is a Django Project?

✅ A **Django project** is the main container for your website or web application.  
It contains all the configuration and settings needed to run your site.

Think of it as the starting point of your website.

---

## 🔷 How to Create a Django Project

### ✅ Step 1: Open Your Terminal

Go to the folder where you want to create your project.  
For example, on your desktop:
```bash
cd Desktop
```

---

### ✅ Step 2: Run the `startproject` Command

In your terminal, type:
```bash
django-admin startproject backend
```

✅ This creates a folder called `backend/` with the basic Django project structure.

---

### ✅ Step 3: Move Into the Project Folder

Navigate into your new project folder:
```bash
cd backend
```

Inside, you’ll see files like:
```
backend/
├── manage.py
├── backend/
│   ├── settings.py
│   ├── urls.py
│   └── ...
```

---

### ✅ Step 4: Run the Development Server

Start the server to see your project running:
```bash
python manage.py runserver
```

✅ You’ll see something like:
```
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```

---

### ✅ Step 5: Open in Your Browser

Go to:  
🌐 [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

🎉 You’ll see Django’s welcome page:  
**“The install worked successfully! Congratulations!”**

---

## 🏁 Summary: What & How

✅ **What is it?**
- The main folder and setup for your Django website.

✅ **How to create it?**
1. Run: `django-admin startproject backend`
2. Move into folder: `cd backend`
3. Start server: `python manage.py runserver`
4. Open: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

🎉 That’s it — you’ve created and run your first Django project!

🔗 Learn more: [https://docs.djangoproject.com/en/stable/intro/tutorial01/](https://docs.djangoproject.com/en/stable/intro/tutorial01/)
