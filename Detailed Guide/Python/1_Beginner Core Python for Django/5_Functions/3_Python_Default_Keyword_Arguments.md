# Python Basics: Default & Keyword Arguments

In this lesson, you’ll learn:

- What **default arguments** are
- What **keyword arguments** are
- How and when to use them in your functions

These concepts make your functions **flexible** and **easy to use**.

---

## 1. Default Arguments

Default arguments are parameters that have a **default value**.  
If no argument is provided for them, the default value is used.

### **Syntax**

```python
def function_name(param1, param2=value):
    # code block
```

### **Example**

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()           # Uses default value: Guest
greet("Alice")    # Overrides default value
```

Output:

```
Hello, Guest!
Hello, Alice!
```

✔ **Why use default arguments?**

- To provide **optional parameters**.
- To avoid errors when arguments are missing.

---

## 2. Keyword Arguments

Keyword arguments allow you to **specify arguments by name** when calling a function.  
This makes your code **clearer** and lets you **change the order** of arguments.

### **Example**

```python
def full_name(first, last):
    print(f"{first} {last}")

# Using keyword arguments
full_name(last="Smith", first="John")
```

Output:

```
John Smith
```

✔ **Benefits of keyword arguments:**

- More readable code.
- Avoids mistakes when passing multiple arguments.

---

## 3. Combining Default & Keyword Arguments

You can use both together for **maximum flexibility**.

### **Example**

```python
def introduce(name, age=18, city="Unknown"):
    print(f"Name: {name}, Age: {age}, City: {city}")

# Call with positional arguments
introduce("Alice")

# Call with keyword arguments
introduce("Bob", city="New York")

# Call with all arguments
introduce(name="Charlie", age=25, city="London")
```

Output:

```
Name: Alice, Age: 18, City: Unknown
Name: Bob, Age: 18, City: New York
Name: Charlie, Age: 25, City: London
```

---

## Best Practices

✔ Put **default arguments after required arguments**:

```python
def example(a, b=10):  # Correct
    pass
```

❌ Wrong:

```python
def example(a=10, b):  # Not allowed
    pass
```

---

### Key Takeaways

✔ **Default arguments** provide fallback values.  
✔ **Keyword arguments** improve readability and flexibility.  
✔ Always place required arguments first, then default ones.

---
