# Python Basics: Function Parameters and Return Values

Welcome! In this lesson, you’ll learn:

- What **parameters** are
- How **return values** work
- Why they are important in functions

Understanding these concepts will make your functions more flexible and powerful.

---

## 1. What are Parameters?

**Parameters** are variables inside the parentheses of a function definition.  
They let you **pass information** into the function.

### **Example**

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")
greet("Bob")
```

Output:

```
Hello, Alice!
Hello, Bob!
```

✔ Here:

- `name` is a **parameter** in the function.
- `"Alice"` and `"Bob"` are **arguments** passed when calling the function.

---

## 2. Types of Parameters

### **a) Positional Parameters**

The order of arguments matters.

```python
def full_name(first, last):
    print(f"{first} {last}")

full_name("John", "Doe")
```

### **b) Default Parameters**

Provide a default value if no argument is given.

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()           # Hello, Guest!
greet("Charlie")  # Hello, Charlie!
```

---

## 3. What is a Return Value?

Functions can **send a value back** using `return`.  
Unlike `print()`, `return` gives the value back to the caller for further use.

### **Example**

```python
def add(a, b):
    return a + b

result = add(5, 3)
print(result)
```

Output:

```
8
```

✔ Why `return` is useful:

- You can **store the result** in a variable.
- You can use it in **other calculations**.

---

## 4. Function Without Return

If you don’t use `return`, the function returns `None` by default.

### **Example**

```python
def say_hello():
    print("Hello!")

result = say_hello()
print(result)  # None
```

---

## 5. Combining Parameters and Return

```python
def calculate_area(length, width):
    return length * width

area = calculate_area(5, 3)
print(f"Area: {area}")
```

Output:

```
Area: 15
```

---

### Key Takeaways

✔ **Parameters** pass data into a function.  
✔ **Arguments** are the actual values you send when calling the function.  
✔ **return** sends data back from the function.  
✔ Use `return` for reusable and flexible code.

---
