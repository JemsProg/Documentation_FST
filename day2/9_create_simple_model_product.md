# 🛍️ How to Create a Simple Model in Django (Beginner-Friendly Guide)

If you want to store data in a database, you define a **model** in Django.  
Here’s **what a model is, and how to create a simple Product model step by step.**

---

## ❓ What is a Django Model?

✅ A **model** is a Python class that represents a table in your database.  
Each attribute (variable) in the class is a column in the table.

For example:
- The `Product` model will represent products.
- Each product has a name and a price.

---

## 🔷 How to Create a Simple Model

### ✅ Step 1: Open `models.py`

Go to your app folder (e.g., `base/`) and open:
📄 `base/models.py`

---

### ✅ Step 2: Define the Product Model

Inside `models.py`, write this code:

```python
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=100)
    price = models.DecimalField(max_digits=6, decimal_places=2)
```

---

## 🔷 What Does This Code Do?

✅ It creates a model (database table) called **Product** with two columns:
- `name`: a text field (max 100 characters)
- `price`: a decimal number (up to 9999.99)

---

### ✅ Step 3: Make Migrations

After saving the file, you need to tell Django to create the table in the database.

Run:
```bash
python manage.py makemigrations
```

Then apply it:
```bash
python manage.py migrate
```

Now Django creates the `Product` table.

---

## 🏁 Summary: What & How

✅ **What is it?**
- A Django model is a Python class that defines what data you store in your database.

✅ **How to create it?**
1. Open `models.py`.
2. Write your model class.
3. Run: `python manage.py makemigrations`.
4. Run: `python manage.py migrate`.

🎉 That’s it — your Product model is ready to use!

🔗 Learn more: [https://docs.djangoproject.com/en/stable/topics/db/models/](https://docs.djangoproject.com/en/stable/topics/db/models/)
