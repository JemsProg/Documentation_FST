# Python Basics: requirements.txt (Managing Project Dependencies)

In this lesson, you’ll learn:

- What `requirements.txt` is
- Why it’s important
- How to create and use it in your projects

This file is essential for **sharing and deploying Python projects**.

---

## 1. What is requirements.txt?

`requirements.txt` is a **text file that lists all the Python packages your project needs**.  
It allows other developers (or servers) to **install the exact same dependencies**.

✔ Commonly used in:

- **Team projects**
- **Deploying to production**
- **Open-source projects**

---

## 2. Why Use requirements.txt?

✔ Keeps track of all installed packages.  
✔ Makes project **portable** (easy to share and deploy).  
✔ Ensures consistent versions of packages.

---

## 3. How to Create requirements.txt

First, activate your **virtual environment** and install your packages:

```bash
pip install django djangorestframework
```

Then, generate `requirements.txt`:

```bash
pip freeze > requirements.txt
```

✔ This saves all installed packages and their versions.

Example of `requirements.txt`:

```
Django==4.2
djangorestframework==3.14
```

---

## 4. How to Install from requirements.txt

If someone else wants to run your project:

1. Create and activate a **virtual environment**.
2. Run:

```bash
pip install -r requirements.txt
```

✔ This installs **all the listed packages** with exact versions.

---

## 5. Updating requirements.txt

Whenever you install a new package, update the file:

```bash
pip freeze > requirements.txt
```

---

### Key Takeaways

✔ `requirements.txt` stores all your project dependencies.  
✔ Use `pip freeze > requirements.txt` to create it.  
✔ Use `pip install -r requirements.txt` to install from it.

---
