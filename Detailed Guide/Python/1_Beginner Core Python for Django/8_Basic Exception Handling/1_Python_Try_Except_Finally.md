# Python Basics: try, except, finally (Exception Handling)

In this lesson, you’ll learn:

- What **exceptions** are
- How to handle errors using **try** and **except**
- Why and how to use **finally**

These concepts are important for writing **safe and error-free code**.

---

## 1. What is an Exception?

An **exception** is an error that occurs during program execution.  
If not handled, it will **stop the program**.

Example of an error:

```python
print(10 / 0)  # ZeroDivisionError
```

Output:

```
ZeroDivisionError: division by zero
```

✔ To prevent crashes, we use **exception handling**.

---

## 2. Using try and except

The `try` block lets you **test code for errors**,  
and the `except` block handles the error gracefully.

### **Syntax**

```python
try:
    # Code that might cause an error
except:
    # Code to run if there is an error
```

### **Example**

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)
except:
    print("Something went wrong!")
```

✔ If the user enters `0` or non-numeric input, it won’t crash.

---

## 3. Catch Specific Exceptions

It’s a good practice to catch **specific errors**.

### **Example**

```python
try:
    num = int("abc")
except ValueError:
    print("Invalid number format!")
```

---

## 4. Using finally

The `finally` block always runs, **whether there was an error or not**.  
Used for **cleanup actions** (like closing files or releasing resources).

### **Example**

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("Cannot divide by zero!")
except ValueError:
    print("Please enter a valid number!")
finally:
    print("Execution finished.")
```

Output (if input is 0):

```
Cannot divide by zero!
Execution finished.
```

✔ `finally` is useful for cleanup:

- Closing database connections
- Closing files
- Releasing resources

---

## 5. Why Use Exception Handling?

✔ Prevents program from crashing.  
✔ Gives user-friendly error messages.  
✔ Handles unexpected inputs or system errors.

---

### Key Takeaways

✔ Use **try** for risky code.  
✔ Use **except** to handle errors gracefully.  
✔ Use **finally** for cleanup tasks that should always happen.

---
