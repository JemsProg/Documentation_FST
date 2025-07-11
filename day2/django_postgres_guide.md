# 🌳 Django + PostgreSQL Setup Guide (Railway.app)

This document helps you connect your Django-based e‑commerce system to a PostgreSQL database hosted on [Railway.app](https://railway.app), based on the “Easiest Way To Connect Django To A Postgres Database” tutorial.

---

## 1. Set Up PostgreSQL on Railway

1. Sign up or log in to Railway.app.
2. Create a **new project** and choose **PostgreSQL** as the database.
3. Once provisioned, go to the **Connect** (or **Variables**) tab.
4. Copy the connection details: host, port, database name, username, and password, or get the full **DATABASE_URL**.

---

## 2. Install Required Packages

Activate your virtual environment and run:

```bash
pip install psycopg2
```

- `psycopg2`: PostgreSQL adapter for Django

---

## 3. Update `settings.py`

Replace the default SQLite config with this:

```python


DATABASES = {
    'default':
    {
    'ENGINE': 'django.db.backends.postgresql',
    'NAME': '',
    'USER':  '',
    'PASSWORD':  '',
    'HOST':  '',
    'PORT':  '',
    }
}
```

---

## 4. Migrate Your Database

Run migrations to create tables for your e-commerce models:

```bash
py manage.py migrate
```

Verify the tables appear in Railway’s database dashboard.

---

---

## Summary Table

| Step | Action                                            |
| ---- | ------------------------------------------------- |
| 1    | Provision Postgres on Railway                     |
| 2    | Install `psycopg2-binary` & `dj-database-url`     |
| 3    | Update Django `settings.py` to use `DATABASE_URL` |
| 4    | Run `migrate` to create DB schema                 |

---

### ✅ TL;DR for E‑Commerce Integration

- Your product, order, and customer tables will now store in PostgreSQL instead of SQLite.
- Railway handles your DB’s hosting and scaling.
- Django’s ORM works the same — but now with a robust, production‑grade backend.

---
