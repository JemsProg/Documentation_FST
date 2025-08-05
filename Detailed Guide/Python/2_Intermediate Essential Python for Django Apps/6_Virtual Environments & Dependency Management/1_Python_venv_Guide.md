# Python Basics: venv (Virtual Environment)

In this lesson, you’ll learn:

- What **venv** is
- Why virtual environments are important
- How to create and use a virtual environment in Python

---

## 1. What is venv?

`venv` stands for **Virtual Environment** in Python.  
It is a tool to create an **isolated environment** for your project, so your dependencies do not conflict with other projects.

✔ Without `venv`, all packages install **globally**, which can cause **version conflicts**.  
✔ With `venv`, you install packages **only for that project**.

---

## 2. Why Use a Virtual Environment?

✔ Keeps dependencies **separate** for each project.  
✔ Prevents **package version conflicts**.  
✔ Makes your project easier to **share** using `requirements.txt`.

---

## 3. How to Create a Virtual Environment

Navigate to your project folder and run:

```bash
python3 -m venv venv
```

✔ This will create a folder named **venv** inside your project.

---

## 4. How to Activate venv

Before using it, you must **activate** it.

### **On Windows**

```powershell
venv\Scriptsctivate
```

### **On macOS / Linux**

```bash
source venv/bin/activate
```

✔ When activated, your terminal will show `(venv)` like this:

```
(venv) C:\YourProject>
```

---

## 5. How to Install Packages Inside venv

Once activated, use `pip` to install packages:

```bash
pip install django
```

✔ Packages installed here will **not affect global Python**.

---

## 6. Deactivate venv

When you’re done, deactivate the virtual environment:

```bash
deactivate
```

---

## 7. Save Dependencies with requirements.txt

To share your project dependencies:

```bash
pip freeze > requirements.txt
```

To install from that file:

```bash
pip install -r requirements.txt
```

---

### Key Takeaways

✔ Use `python3 -m venv venv` to create an environment.  
✔ Activate it before installing packages.  
✔ Use `pip freeze > requirements.txt` for sharing dependencies.

---
