# Python Basics: Custom Decorators

In this lesson, you’ll learn:

- What a **decorator** is
- How to create your own **custom decorator**
- Why decorators are useful in Python

Decorators allow you to **add extra functionality** to existing functions without modifying their code.

---

## 1. What is a Decorator?

A **decorator** is a function that:

- Takes another function as input.
- Adds some functionality to it.
- Returns the modified function.

✔ Common use: Logging, authentication checks, timing function execution.

---

## 2. Basic Decorator Example

### Without decorator:

```python
def greet():
    print("Hello!")

greet()
```

---

## 3. Creating a Simple Decorator

### **Step 1: Define a decorator function**

```python
def my_decorator(func):
    def wrapper():
        print("Before the function runs")
        func()
        print("After the function runs")
    return wrapper
```

### **Step 2: Apply the decorator**

```python
@my_decorator
def greet():
    print("Hello!")

greet()
```

Output:

```
Before the function runs
Hello!
After the function runs
```

✔ The decorator added **extra behavior** without changing `greet()`.

---

## 4. Decorators with Arguments

If your function has parameters, the wrapper needs to accept them.

### **Example**

```python
def my_decorator(func):
    def wrapper(*args, **kwargs):
        print("Function is about to run...")
        result = func(*args, **kwargs)
        print("Function has finished.")
        return result
    return wrapper

@my_decorator
def add(a, b):
    return a + b

print(add(5, 3))
```

Output:

```
Function is about to run...
Function has finished.
8
```

✔ We use `*args` and `**kwargs` to handle any number of arguments.

---

## 5. Why Use Custom Decorators?

✔ To **reuse functionality** like logging or authentication.  
✔ To **keep code clean and modular**.  
✔ Common in **Django**, **Flask**, and **APIs** (for permissions, caching, etc.).

---

## 6. Real-Life Example: Logging

```python
def log_function(func):
    def wrapper(*args, **kwargs):
        print(f"Running {func.__name__} with arguments {args}")
        return func(*args, **kwargs)
    return wrapper

@log_function
def multiply(x, y):
    return x * y

print(multiply(4, 5))
```

Output:

```
Running multiply with arguments (4, 5)
20
```

---

### Key Takeaways

✔ A decorator wraps a function to **add extra behavior**.  
✔ Use `@decorator_name` to apply it easily.  
✔ Use `*args` and `**kwargs` for flexible arguments.

---
