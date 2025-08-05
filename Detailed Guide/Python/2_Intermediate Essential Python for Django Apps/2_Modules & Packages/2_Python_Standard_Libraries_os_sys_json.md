# Python Basics: Python Standard Libraries (os, sys, json)

In this lesson, you’ll learn:

- What **standard libraries** are
- How to use `os`, `sys`, and `json` modules
- Why these libraries are useful in real-world programs

Python comes with **built-in modules** that provide ready-to-use functionality.

---

## 1. What are Standard Libraries?

Standard libraries are **built-in modules** included with Python.  
✔ No need to install them separately.  
✔ They help with tasks like file handling, system operations, and working with data formats.

---

## 2. The os Module

The `os` module provides functions to **interact with the operating system**.

### **Common Functions**

```python
import os

# Get current working directory
print(os.getcwd())

# List files in current directory
print(os.listdir())

# Create a new directory
os.mkdir("test_folder")

# Remove a directory
os.rmdir("test_folder")
```

✔ Useful for **file management** in automation scripts.

---

## 3. The sys Module

The `sys` module provides functions and variables to **interact with the Python interpreter**.

### **Common Uses**

```python
import sys

# Get Python version
print(sys.version)

# Get command-line arguments
print(sys.argv)
```

✔ `sys.argv` is important for command-line programs.

---

## 4. The json Module

The `json` module allows you to **work with JSON data** (JavaScript Object Notation).  
✔ JSON is widely used for **APIs and data exchange**.

### **Convert Python to JSON (Serialization)**

```python
import json

data = {"name": "Alice", "age": 25}
json_string = json.dumps(data)
print(json_string)  # {"name": "Alice", "age": 25}
```

### **Convert JSON to Python (Deserialization)**

```python
json_data = '{"name": "Bob", "age": 30}'
python_data = json.loads(json_data)
print(python_data["name"])  # Bob
```

✔ `dumps` = Python → JSON  
✔ `loads` = JSON → Python

---

## 5. Why Use These Libraries?

✔ **os** → File & directory operations  
✔ **sys** → System-level info and arguments  
✔ **json** → Work with API data in Django REST Framework

---

### Key Takeaways

✔ Python includes many built-in modules (no installation needed).  
✔ Use `os` for file system tasks.  
✔ Use `sys` for system-level info and command-line arguments.  
✔ Use `json` for APIs and data exchange.

---
