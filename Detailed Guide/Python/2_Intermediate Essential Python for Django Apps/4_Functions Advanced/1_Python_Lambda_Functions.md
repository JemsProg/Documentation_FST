# Python Basics: Lambda Functions

In this lesson, you’ll learn:

- What **lambda functions** are
- Why they are used
- How to create and use them in Python

Lambda functions are **short, anonymous functions** commonly used for simple operations.

---

## 1. What is a Lambda Function?

A **lambda function** is a small, anonymous function without a name.  
It is used for **short, simple tasks** where defining a full function with `def` would be unnecessary.

### **Syntax**

```python
lambda arguments: expression
```

✔ The expression is automatically returned (no need for `return`).

---

## 2. Why Use Lambda Functions?

✔ To create quick, one-time-use functions.  
✔ Common in **functional programming**, with `map()`, `filter()`, `sorted()`.

---

## 3. Example: Normal Function vs Lambda

### Normal function:

```python
def add(a, b):
    return a + b

print(add(5, 3))  # 8
```

### Lambda function:

```python
add = lambda a, b: a + b
print(add(5, 3))  # 8
```

✔ Both do the same thing, but the lambda is shorter.

---

## 4. Using Lambda with map(), filter(), reduce()

### **a) map()** → Apply function to each element

```python
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x**2, numbers))
print(squared)  # [1, 4, 9, 16]
```

### **b) filter()** → Filter based on condition

```python
numbers = [10, 15, 20, 25]
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # [10, 20]
```

### **c) reduce()** → Combine all elements (requires functools)

```python
from functools import reduce
numbers = [1, 2, 3, 4]
sum_all = reduce(lambda a, b: a + b, numbers)
print(sum_all)  # 10
```

---

## 5. Limitations of Lambda

✔ Good for short tasks, but **not for complex logic**.  
✔ If your function needs multiple lines → use `def`.

---

### Key Takeaways

✔ Lambda functions are **anonymous, one-liner functions**.  
✔ Syntax: `lambda arguments: expression`.  
✔ Useful with `map()`, `filter()`, and `reduce()`.

---
