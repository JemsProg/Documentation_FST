# 🗃️ How to Run `makemigrations` and `migrate` in Django (Beginner-Friendly Guide)

When you create or update a Django model, you need to tell Django to update the database.  
Here’s **what `makemigrations` and `migrate` mean, and how to use them step by step.**

---

## ❓ What Are `makemigrations` and `migrate`?

✅ **`makemigrations`**: Prepares a plan for changes to your database, based on your models.  
✅ **`migrate`**: Actually applies those changes to your database.

Think of it like:
- `makemigrations` = plan 📝
- `migrate` = execute 🚀

---

## 🔷 Why Are They Needed?

Whenever you:
- Create a new model
- Add or remove a field
- Change field options

You have to sync your database with your Python code using these two commands.

---

## 🔷 How to Run Them

### ✅ Step 1: Make Migrations

In your terminal, inside your project folder, type:

```bash
python manage.py makemigrations
```

✅ Output will look like this:
```
Migrations for 'base':
  base/migrations/0001_initial.py
    - Create model Product
```

This creates a migration file (a plan) in your app’s `migrations/` folder.

---

### ✅ Step 2: Apply the Migrations

Now apply the migration plan to the database:

```bash
python manage.py migrate
```

✅ Output will look like this:
```
Applying base.0001_initial... OK
```

---

## 🏁 Summary: What & How

✅ **What are they?**
- `makemigrations`: Creates a migration plan (but doesn’t change the database yet).
- `migrate`: Executes the plan and updates the database.

✅ **How to use them?**
1. Run: `python manage.py makemigrations`
2. Run: `python manage.py migrate`

🎉 That’s it — your database is now in sync with your models!

🔗 Learn more: [https://docs.djangoproject.com/en/stable/topics/migrations/](https://docs.djangoproject.com/en/stable/topics/migrations/)
