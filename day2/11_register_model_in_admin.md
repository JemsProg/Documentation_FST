# 🖋️ How to Register a Model in `admin.py` (Beginner-Friendly Guide)

Django comes with a built-in **admin panel** where you can manage your data through a web interface.  
Here’s **what it means to register a model in `admin.py`, and how to do it step by step.**

---

## ❓ What Does Registering a Model Mean?

✅ By default, your models (like `Product`) are not visible in the Django admin panel.  
✅ Registering a model in `admin.py` tells Django:  
*"Show this model in the admin so I can add, edit, and delete records easily."*

---

## 🔷 How to Register a Model

### ✅ Step 1: Open `admin.py`

Go to your app folder (e.g., `base/`) and open:  
📄 `base/admin.py`

---

### ✅ Step 2: Import Your Model

At the top of the file, import your model:

```python
from .models import Product
```

---

### ✅ Step 3: Register the Model

Below the import, add this line:

```python
admin.site.register(Product)
```

✅ Now your `admin.py` should look like this:

```python
from django.contrib import admin
from .models import Product

admin.site.register(Product)
```

---

### ✅ Step 4: Run the Server and Login

Start your development server:
```bash
python manage.py runserver
```

Go to: 🌐 [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)

Log in with your superuser account (use `python manage.py createsuperuser` if you haven’t created one yet).

✅ You should now see **Product** in the list of models!

---

## 🏁 Summary: What & How

✅ **What is it?**
- Registering a model makes it appear in the Django admin so you can manage its data easily.

✅ **How to do it?**
1. Open `admin.py`
2. Import your model
3. Use: `admin.site.register(YourModel)`
4. Login to `/admin/` and see your model

🎉 That’s it — your model is now manageable through the Django admin!

🔗 Learn more: [https://docs.djangoproject.com/en/stable/ref/contrib/admin/](https://docs.djangoproject.com/en/stable/ref/contrib/admin/)
