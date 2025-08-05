# Python Basics: Comments, Indentation, and Variables

Welcome! In this lesson, you’ll learn three fundamental concepts in Python:

- **Comments** (How to write notes in your code)
- **Indentation** (How Python organizes code blocks)
- **Variables** (How to store and use data)

These are the building blocks for writing clean and readable Python programs.

---

## 1. Comments in Python

**What are comments?**
Comments are notes in your code that Python **ignores during execution**. They help you explain what your code does.

### **Types of Comments**

✔ **Single-line Comment**

```python
# This is a single-line comment
print("Hello World")  # This prints text to the screen
```

✔ **Multi-line Comment**
Python doesn’t have a specific multi-line comment syntax, but you can use triple quotes:

```python
"""
This is a multi-line comment.
Useful for explaining big code sections.
"""
print("Hello Python!")
```

**Why use comments?**
✔ Make code easier to understand.  
✔ Helpful when working in teams.  
✔ Future YOU will thank present YOU!

---

## 2. Indentation in Python

Unlike other languages (like Java or C), Python uses **indentation (spaces or tabs)** to define code blocks.

✔ Example:

```python
if True:
    print("This is indented correctly")
```

❌ Wrong indentation will cause an error:

```python
if True:
print("This will cause an IndentationError")
```

**Rule of Thumb:**
✔ Use **4 spaces** per indentation level (PEP8 standard).  
✔ Be consistent (don’t mix tabs and spaces).

---

## 3. Variables in Python

**What is a variable?**
A variable is a **name that stores a value** in memory. It allows you to reuse values in your program.

### **How to create a variable**

```python
name = "John"  # String
age = 25       # Integer
price = 19.99  # Float
is_student = True  # Boolean
```

✔ Python is **dynamically typed**, meaning you **don’t need to declare types** explicitly:

```python
x = 10        # Integer
x = "Hello"   # Now x is a String
```

### **Naming Rules**

✔ Start with a letter or underscore (`_`).  
✔ Can contain letters, numbers, and underscores.  
✔ Case-sensitive (`Name` ≠ `name`).  
✔ **Avoid keywords** (like `for`, `if`, `class`).

### **Good vs Bad Naming**

✔ Good: `student_name`, `total_price`  
❌ Bad: `a`, `b`, `data1234`

---

## Examples

```python
# Example of comments, indentation, and variables

# This program greets a user
user_name = "Alice"  # Store user name
print("Hello,", user_name)  # Print greeting
```

Output:

```
Hello, Alice
```

---

### Key Takeaways

✔ Comments make your code readable.  
✔ Indentation defines your code structure in Python.  
✔ Variables store data and follow naming rules.

---
