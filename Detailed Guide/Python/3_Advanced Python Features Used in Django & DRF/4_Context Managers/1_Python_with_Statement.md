# Python Basics: Using the with Statement

In this lesson, you’ll learn:

- What the **with statement** is
- Why it’s used in Python
- How to use it for file handling and resource management

The `with` statement is commonly used for **clean and safe resource handling**.

---

## 1. What is the with Statement?

The `with` statement simplifies **resource management**.  
When you work with resources like **files or network connections**, they need to be **closed properly** after use.

✔ `with` automatically:

- Opens the resource.
- Executes your code block.
- Closes the resource (even if an error occurs).

---

## 2. Why Use with Instead of open()?

Without `with`:

```python
file = open("example.txt", "r")
content = file.read()
file.close()  # Must close manually
```

If you **forget** to call `close()`, the file stays open, which can cause problems.

---

Using `with`:

```python
with open("example.txt", "r") as file:
    content = file.read()

# File is automatically closed here
```

✔ Cleaner and safer.

---

## 3. Syntax

```python
with expression [as variable]:
    # block of code
```

---

## 4. Example: Reading a File

```python
with open("data.txt", "r") as f:
    content = f.read()
    print(content)
```

✔ After the block ends, the file **closes automatically**.

---

## 5. Example: Writing to a File

```python
with open("data.txt", "w") as f:
    f.write("Hello, Python!")
```

✔ No need to call `f.close()`.

---

## 6. Using with for Multiple Files

```python
with open("file1.txt", "r") as f1, open("file2.txt", "w") as f2:
    data = f1.read()
    f2.write(data)
```

✔ Both files close automatically.

---

## 7. Why is with Important?

✔ Prevents **resource leaks**.  
✔ Handles **exceptions safely**.  
✔ Makes code **cleaner and shorter**.

---

### Key Takeaways

✔ Use `with` for file operations.  
✔ It automatically handles resource cleanup.  
✔ Useful for files, database connections, and more.

---
