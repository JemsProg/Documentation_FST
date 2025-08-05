# Python Basics: PEP 8 Guidelines

In this lesson, you’ll learn:

- What **PEP 8** is
- Why it’s important
- Key rules from PEP 8 that every Python developer should follow

---

## 1. What is PEP 8?

PEP 8 stands for **Python Enhancement Proposal 8**.  
It is the **official style guide for Python code**.

✔ Goal: Make Python code **readable**, **consistent**, and **professional**.  
✔ Following PEP 8 is important for:

- **Team projects**
- **Open-source contributions**
- **Interview and job readiness**

---

## 2. Why Follow PEP 8?

✔ Improves **code readability**.  
✔ Makes your code **consistent** with other Python projects.  
✔ Helps avoid **confusion in large projects**.

---

## 3. Key PEP 8 Guidelines

### a) Indentation

✔ Use **4 spaces per indentation level**.

```python
if True:
    print("Follow PEP 8")
```

---

### b) Line Length

✔ Keep lines **≤ 79 characters**.
✔ For docstrings/comments, **≤ 72 characters**.

---

### c) Blank Lines

✔ Use blank lines to separate:

- **Functions** → 2 blank lines
- **Methods inside a class** → 1 blank line

Example:

```python
def func1():
    pass


def func2():
    pass
```

---

### d) Imports

✔ Put imports at the **top of the file**.  
✔ One import per line.

```python
import os
import sys
```

✔ Group imports in this order:

1. Standard libraries
2. Third-party libraries
3. Local application imports

---

### e) Spaces Around Operators

✔ Add spaces around **assignment** and **comparison** operators.

```python
x = 10  # Correct
x=10    # Wrong
```

✔ No extra spaces inside parentheses or brackets.

```python
list1 = [1, 2, 3]  # Correct
list1 = [ 1, 2, 3 ]  # Wrong
```

---

### f) Naming Conventions

✔ Variables & functions → **snake_case**:

```python
user_name = "Alice"
```

✔ Classes → **PascalCase**:

```python
class MyClass:
    pass
```

✔ Constants → **UPPER_CASE**:

```python
PI = 3.14
```

---

### g) Comments and Docstrings

✔ Use `#` for single-line comments.
✔ Use **triple quotes** for docstrings.

```python
def add(a, b):
    """Return the sum of two numbers."""
    return a + b
```

---

### h) Avoid Unnecessary Code

✔ No extra semicolons:

```python
print("Hello")  # Correct
print("Hello");  # Wrong
```

✔ No unused imports or variables.

---

## 4. Tools to Check PEP 8

✔ **flake8**

```bash
pip install flake8
flake8 yourfile.py
```

✔ **black** (auto-formatting)

```bash
pip install black
black yourfile.py
```

---

### Key Takeaways

✔ Use **4 spaces**, keep **line length ≤ 79 chars**, and follow naming rules.  
✔ Write **readable, clean, and consistent** code.  
✔ Use tools like **flake8** and **black** to enforce style.

---
