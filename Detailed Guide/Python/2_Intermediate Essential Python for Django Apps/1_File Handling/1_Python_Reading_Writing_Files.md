# Python Basics: Reading and Writing Files

In this lesson, you’ll learn:

- How to **open files** in Python
- How to **read from files**
- How to **write to files**
- Why file handling is important

File handling is essential when working with **data storage**, **logs**, or **configuration files**.

---

## 1. Why File Handling?

Programs often need to:
✔ Save data permanently (not just in memory).  
✔ Read existing information from a file.

Example:

- A student management system storing student names in a file.

---

## 2. Opening a File

Use the built-in `open()` function:

```python
open("filename", "mode")
```

### **Common modes**

| Mode | Description                   |
| ---- | ----------------------------- |
| `r`  | Read (default)                |
| `w`  | Write (creates or overwrites) |
| `a`  | Append (adds to file)         |
| `r+` | Read and Write                |

---

## 3. Reading from a File

### **Example**

```python
file = open("example.txt", "r")  # Open in read mode
content = file.read()
print(content)
file.close()
```

✔ Use `read()` to read the entire file.  
✔ Use `readline()` to read one line.  
✔ Use `readlines()` to read all lines into a list.

---

## 4. Writing to a File

### **Example**

```python
file = open("example.txt", "w")  # Open in write mode
file.write("Hello, World!")
file.close()
```

✔ If the file does not exist, Python creates it.  
✔ Using `w` will **overwrite** existing content.  
✔ Use `a` (append) to add new content without deleting the old one:

```python
file = open("example.txt", "a")
file.write("\nThis is a new line.")
file.close()
```

---

## 5. Using with Statement (Best Practice)

Using `with` automatically closes the file after use:

```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

✔ No need to call `file.close()`.

---

## 6. Writing Multiple Lines

```python
lines = ["First line\n", "Second line\n", "Third line\n"]
with open("example.txt", "w") as file:
    file.writelines(lines)
```

---

## 7. Reading Files Line by Line

```python
with open("example.txt", "r") as file:
    for line in file:
        print(line.strip())  # strip() removes newline
```

---

### Key Takeaways

✔ Use `open()` with correct mode (`r`, `w`, `a`).  
✔ Always close files or use `with` for safety.  
✔ `read()`, `readline()`, and `readlines()` help you read files in different ways.  
✔ Writing to a file will **overwrite** by default unless you use append mode.

---
