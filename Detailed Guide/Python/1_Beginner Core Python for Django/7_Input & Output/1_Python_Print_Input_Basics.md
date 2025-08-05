# Python Basics: print() and input() Functions

In this lesson, you’ll learn:

- How to display output using **print()**
- How to take user input using **input()**
- Why these two functions are important for Python programs

These are the most basic and essential functions for interaction with your program.

---

## 1. The print() Function

The `print()` function is used to **display information on the screen**.

### **Syntax**

```python
print(value1, value2, ..., sep=' ', end='\n')
```

- `value1, value2`: Values you want to display.
- `sep`: Separator between values (default is a space).
- `end`: What to print at the end (default is newline `\n`).

### **Example**

```python
print("Hello, World!")
print("Python", "is", "fun")
```

Output:

```
Hello, World!
Python is fun
```

### **Using sep and end**

```python
print("A", "B", "C", sep="-")   # A-B-C
print("Line 1", end=" | ")      # Replaces newline
print("Line 2")                 # Output: Line 1 | Line 2
```

---

## 2. The input() Function

The `input()` function is used to **take input from the user** as a **string**.

### **Syntax**

```python
variable = input("Enter your text: ")
```

### **Example**

```python
name = input("What is your name? ")
print(f"Hello, {name}!")
```

✔ Whatever you type will be stored in `name`.

---

## 3. input() Always Returns a String

Even if you type a number, it will be a string.  
✔ To convert to an integer or float, use `int()` or `float()`.

### **Example**

```python
age = input("Enter your age: ")
print(type(age))  # <class 'str'>

# Convert to integer
age = int(age)
print(type(age))  # <class 'int'>
```

---

## 4. Combining print() and input()

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
print(f"Hello {name}, you are {age} years old!")
```

---

### Key Takeaways

✔ `print()` displays text or variables on the screen.  
✔ `input()` takes user input as **string** (convert if needed).  
✔ Use **f-strings** for clean output formatting.

---
