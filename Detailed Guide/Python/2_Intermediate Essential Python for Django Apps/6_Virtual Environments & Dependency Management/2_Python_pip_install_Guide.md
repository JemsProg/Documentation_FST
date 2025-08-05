# Python Basics: pip install (Package Management)

In this lesson, you’ll learn:

- What **pip** is
- How to install Python packages using `pip install`
- How to manage dependencies for your project

---

## 1. What is pip?

`pip` is the **Python Package Installer**.  
It allows you to **install, update, and manage Python packages** from the Python Package Index (PyPI).

✔ Example: Install Django, Flask, or any third-party library.  
✔ Comes pre-installed with Python (3.4+).

---

## 2. Check if pip is Installed

Run this command:

```bash
pip --version
```

Output example:

```
pip 23.x.x from /usr/lib/python3.x/site-packages (python 3.x)
```

---

## 3. Installing a Package

The basic command is:

```bash
pip install package_name
```

### **Example**

```bash
pip install django
```

✔ This installs the **latest version** of Django.

---

## 4. Installing a Specific Version

Use `==` to specify the version:

```bash
pip install django==4.2
```

✔ Useful for maintaining compatibility in projects.

---

## 5. Upgrading a Package

Use `--upgrade` or `-U`:

```bash
pip install --upgrade django
```

---

## 6. Installing Multiple Packages

You can install multiple packages in one command:

```bash
pip install requests pillow flask
```

---

## 7. Uninstalling a Package

```bash
pip uninstall django
```

---

## 8. Checking Installed Packages

```bash
pip list
```

---

## 9. Using requirements.txt

✔ Save all installed packages:

```bash
pip freeze > requirements.txt
```

✔ Install all packages from file:

```bash
pip install -r requirements.txt
```

---

### Key Takeaways

✔ `pip install package_name` installs packages from PyPI.  
✔ Use `requirements.txt` to share dependencies.  
✔ Always use `pip` inside a **virtual environment (venv)**.

---
