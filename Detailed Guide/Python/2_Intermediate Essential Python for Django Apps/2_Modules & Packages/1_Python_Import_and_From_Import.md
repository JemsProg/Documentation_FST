# Python Basics: import and from ... import

In this lesson, you’ll learn:

- How to **import modules** in Python
- The difference between `import` and `from ... import`
- Why importing is important in Python programs

Modules allow you to **reuse code** and **organize programs better**.

---

## 1. What is a Module?

A **module** is a Python file (`.py`) that contains functions, classes, or variables.  
Python has:
✔ **Built-in modules** (like `math`, `random`, `os`)  
✔ **Custom modules** (you create your own Python files and import them)

---

## 2. Why Use import?

✔ To **reuse existing code** (don’t reinvent the wheel).  
✔ To use **standard libraries** (for math, dates, file handling, etc.).

---

## 3. Using import

The `import` statement loads an entire module.

### **Example**

```python
import math

print(math.sqrt(16))  # 4.0
print(math.pi)        # 3.141592653589793
```

✔ Here:

- `math` is the module.
- You call functions using `module_name.function()`.

---

## 4. Using from ... import

The `from` keyword lets you **import specific items** from a module.

### **Example**

```python
from math import sqrt, pi

print(sqrt(25))  # 5.0
print(pi)        # 3.141592653589793
```

✔ No need to use `math.` prefix when using `from ... import`.

---

## 5. Import Everything (Not Recommended)

You can import **all items** using `*`, but it’s not good practice.

```python
from math import *
print(sin(0))  # 0.0
```

✔ Avoid this because it can cause **name conflicts**.

---

## 6. Using as (Alias)

You can rename a module or function using `as`.

### **Example**

```python
import math as m
print(m.sqrt(49))  # 7.0
```

✔ Useful when module names are long.

---

## 7. Importing Custom Modules

You can create your own file, e.g., `mymodule.py`:

```python
def greet(name):
    return f"Hello, {name}!"
```

In another file:

```python
import mymodule
print(mymodule.greet("Alice"))
```

Or:

```python
from mymodule import greet
print(greet("Alice"))
```

---

### Key Takeaways

✔ `import module` → Import whole module.  
✔ `from module import item` → Import specific function or variable.  
✔ Use **alias (as)** to shorten names.  
✔ Avoid `import *` for clean and safe code.

---
