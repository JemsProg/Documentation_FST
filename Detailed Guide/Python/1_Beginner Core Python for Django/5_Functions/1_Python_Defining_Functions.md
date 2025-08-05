# Python Basics: Defining Functions

Welcome! In this lesson, you’ll learn about **functions** in Python:

- What a function is
- Why we use functions
- How to define and call a function

Functions make your code **organized**, **reusable**, and easier to understand.

---

## 1. What is a Function?

A **function** is a block of code that performs a specific task.  
Functions allow us to **reuse code** instead of writing it again and again.

✔ Example:

- Instead of writing the same calculation 5 times, create a function and call it.

---

## 2. Why Use Functions?

✔ Avoid repetition (DRY: **Don't Repeat Yourself**)  
✔ Make your code modular and easier to maintain  
✔ Improve readability

---

## 3. Defining a Function

Use the `def` keyword to define a function.

### **Syntax**

```python
def function_name():
    # Code to execute
```

### **Example**

```python
def greet():
    print("Hello, welcome to Python!")

# Calling the function
greet()
```

Output:

```
Hello, welcome to Python!
```

---

## 4. Functions with Parameters

Functions can take **input values** called **parameters**.

### **Example**

```python
def greet_user(name):
    print(f"Hello, {name}!")

greet_user("Alice")
```

Output:

```
Hello, Alice!
```

✔ Parameters allow the function to work with different data.

---

## 5. Functions with Return Values

Functions can return a value using `return`.

### **Example**

```python
def add_numbers(a, b):
    return a + b

result = add_numbers(5, 3)
print(result)
```

Output:

```
8
```

---

## 6. Default Parameter Values

You can assign **default values** to parameters.

### **Example**

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()           # Uses default value
greet("Charlie")  # Overrides default
```

Output:

```
Hello, Guest!
Hello, Charlie!
```

---

## 7. Why Use return vs print?

- `print()` → Displays a value on the screen.
- `return` → Sends a value back to the caller (useful for further calculations).

---

## 8. Best Practices

✔ Use meaningful function names.  
✔ Keep functions short and focused on **one task**.

---

### Key Takeaways

✔ Define functions with `def`.  
✔ Use parameters to pass data.  
✔ Use `return` to send a value back.  
✔ Functions make code **reusable and clean**.

---
