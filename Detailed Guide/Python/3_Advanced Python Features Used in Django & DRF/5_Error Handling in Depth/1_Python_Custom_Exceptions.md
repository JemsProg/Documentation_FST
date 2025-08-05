# Python Basics: Custom Exceptions

In this lesson, you’ll learn:

- What exceptions are
- Why we create **custom exceptions**
- How to create and use custom exceptions in Python

Custom exceptions make your programs more **readable, organized, and specific** when handling errors.

---

## 1. What is an Exception?

An **exception** is an error that occurs during program execution.  
Example:

```python
print(10 / 0)  # ZeroDivisionError
```

✔ Python has many built-in exceptions like:

- `ValueError`
- `TypeError`
- `ZeroDivisionError`

---

## 2. Why Create Custom Exceptions?

✔ Built-in exceptions are general (e.g., ValueError).  
✔ Custom exceptions make error messages **clear and specific** to your program.  
✔ Helps in **large projects** where many errors can occur.

---

## 3. How to Create a Custom Exception

Create a new **class** that inherits from `Exception`.

### **Example**

```python
class MyCustomError(Exception):
    pass

# Raise the custom exception
raise MyCustomError("This is a custom error message!")
```

Output:

```
Traceback (most recent call last):
    ...
__main__.MyCustomError: This is a custom error message!
```

---

## 4. Adding Custom Logic

You can add attributes and methods for more details.

### **Example**

```python
class NegativeNumberError(Exception):
    def __init__(self, number, message="Negative numbers are not allowed"):
        self.number = number
        self.message = message
        super().__init__(self.message)

def check_positive(num):
    if num < 0:
        raise NegativeNumberError(num)
    return num

try:
    check_positive(-5)
except NegativeNumberError as e:
    print(f"Error: {e}. Invalid number: {e.number}")
```

Output:

```
Error: Negative numbers are not allowed. Invalid number: -5
```

---

## 5. Why Use Custom Exceptions in Django/DRF?

✔ In APIs, you can return **specific error responses** (e.g., `InvalidEmailError`).  
✔ Improves **debugging** and **error reporting**.

---

### Key Takeaways

✔ Create custom exceptions by inheriting from `Exception`.  
✔ Use `raise` to trigger the exception.  
✔ Use `try-except` to handle them gracefully.

---
