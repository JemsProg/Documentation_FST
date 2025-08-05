# Python Basics: List Comprehensions

In this lesson, you’ll learn:

- What **list comprehensions** are
- Why they are useful
- How to create and use them in Python

List comprehensions make it easy to **create new lists** in a single line of code.

---

## 1. What is a List Comprehension?

A **list comprehension** is a concise way to create a list using a single line of code.  
It combines **loops** and **conditional statements** into one expression.

### **Syntax**

```python
[expression for item in iterable if condition]
```

✔ This replaces writing a `for` loop to create a list.

---

## 2. Why Use List Comprehensions?

✔ Shorter and cleaner than traditional loops.  
✔ Faster and more Pythonic.

---

## 3. Example: Normal Loop vs List Comprehension

### Normal loop:

```python
squares = []
for x in range(5):
    squares.append(x**2)
print(squares)
```

### List comprehension:

```python
squares = [x**2 for x in range(5)]
print(squares)  # [0, 1, 4, 9, 16]
```

---

## 4. Adding Conditions

You can add an **if condition** to filter elements.

### **Example**

```python
evens = [x for x in range(10) if x % 2 == 0]
print(evens)  # [0, 2, 4, 6, 8]
```

---

## 5. Using with Strings

### **Example**

```python
text = "hello"
letters = [char.upper() for char in text]
print(letters)  # ['H', 'E', 'L', 'L', 'O']
```

---

## 6. Nested List Comprehension

You can use **nested loops** inside a list comprehension.

### **Example**

```python
pairs = [(x, y) for x in [1, 2] for y in [3, 4]]
print(pairs)  # [(1, 3), (1, 4), (2, 3), (2, 4)]
```

---

## 7. When NOT to Use List Comprehension

✔ If the logic is too complex → use a normal loop for clarity.

---

### Key Takeaways

✔ List comprehensions provide a **short and efficient** way to create lists.  
✔ Syntax: `[expression for item in iterable if condition]`.  
✔ Use them for **simple, readable logic**.

---
