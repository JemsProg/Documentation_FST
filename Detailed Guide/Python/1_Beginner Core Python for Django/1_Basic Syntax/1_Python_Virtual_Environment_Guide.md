# Python Setup & Virtual Environments (venv)

Welcome to your first step in Python development! In this guide, you’ll learn what **Python virtual environments** are, **why they are important**, and **how to create and use them**.  
This is essential for working with Django and Django REST Framework.

---

## 1. What is a Virtual Environment?

A **virtual environment** is an isolated Python environment where you can install packages **without affecting your system Python installation**.  
This helps avoid conflicts between projects that use different package versions.

✔ Example:

- Project A needs Django 4.2
- Project B needs Django 3.2  
  Without a virtual environment, installing one version will overwrite the other.  
  **Solution:** Each project gets its own virtual environment.

---

## 2. Why Use Virtual Environments?

✔ Keeps your project **dependencies separate**.  
✔ Makes your project **portable** (easy to share with `requirements.txt`).  
✔ Avoids breaking system Python.

---

## 3. How to Set Up Python on Your System

1. **Check Python version**:

```bash
python --version
```

You should see something like:

```
Python 3.x.x
```

If not installed, download from [python.org](https://www.python.org/downloads/).

2. **Check pip (Python package manager)**:

```bash
pip --version
```

---

## 4. Creating a Virtual Environment (venv)

Navigate to your project folder and run:

```bash
python -m venv venv
```

✔ This creates a folder named `venv` in your project directory.

---

## 5. Activating the Virtual Environment

**On Linux / macOS**:

```bash
source venv/bin/activate
```

**On Windows (PowerShell)**:

```powershell
venv\Scripts\activate
```

After activation, you’ll see `(venv)` in your terminal:

```
(venv) user@machine:~/project$
```

---

## 6. Installing Packages Inside venv

Example: Install Django

```bash
pip install django
```

✔ Packages installed here will **not affect global Python**.

---

## 7. Deactivating Virtual Environment

When you’re done, deactivate:

```bash
deactivate
```

---

## 8. Saving Dependencies (requirements.txt)

To share your environment with others:

```bash
pip freeze > requirements.txt
```

To install from that file:

```bash
pip install -r requirements.txt
```

---

### Key Takeaways

✔ Virtual environments keep projects isolated.  
✔ Use `python3 -m venv venv` to create one.  
✔ Always **activate venv before installing packages**.  
✔ Use `requirements.txt` to share dependencies.

---
