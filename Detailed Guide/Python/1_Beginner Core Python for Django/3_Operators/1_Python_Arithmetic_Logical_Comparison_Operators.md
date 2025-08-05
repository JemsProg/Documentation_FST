# Python Basics: Arithmetic, Logical, and Comparison Operators

Welcome! In this lesson, you’ll learn about **three essential types of operators in Python**:

- **Arithmetic Operators** (For mathematical operations)
- **Comparison Operators** (For comparing values)
- **Logical Operators** (For combining conditions)

Operators are symbols or keywords that perform actions on values or variables.

---

## 1. Arithmetic Operators

Arithmetic operators are used for **basic math operations**.

| Operator | Description    | Example       |
| -------- | -------------- | ------------- |
| `+`      | Addition       | `5 + 3 = 8`   |
| `-`      | Subtraction    | `10 - 4 = 6`  |
| `*`      | Multiplication | `6 * 2 = 12`  |
| `/`      | Division       | `8 / 2 = 4.0` |
| `//`     | Floor Division | `9 // 2 = 4`  |
| `%`      | Modulus        | `9 % 2 = 1`   |
| `**`     | Exponentiation | `2 ** 3 = 8`  |

### **Examples**

```python
x = 10
y = 3
print(x + y)    # 13
print(x - y)    # 7
print(x * y)    # 30
print(x / y)    # 3.333...
print(x // y)   # 3
print(x % y)    # 1
print(x ** y)   # 1000
```

---

## 2. Comparison Operators

Comparison operators compare **two values** and return a **Boolean (True/False)**.

| Operator | Description      | Example         |
| -------- | ---------------- | --------------- |
| `==`     | Equal to         | `5 == 5 → True` |
| `!=`     | Not equal to     | `5 != 3 → True` |
| `>`      | Greater than     | `10 > 5 → True` |
| `<`      | Less than        | `3 < 5 → True`  |
| `>=`     | Greater or equal | `7 >= 7 → True` |
| `<=`     | Less or equal    | `4 <= 6 → True` |

### **Examples**

```python
a = 10
b = 20
print(a == b)   # False
print(a != b)   # True
print(a > b)    # False
print(a < b)    # True
print(a >= 10)  # True
print(b <= 20)  # True
```

---

## 3. Logical Operators

Logical operators are used to **combine multiple conditions**.

| Operator | Description                      | Example             |
| -------- | -------------------------------- | ------------------- |
| `and`    | True if both conditions are True | `(a > 5 and b > 5)` |
| `or`     | True if at least one is True     | `(a > 5 or b > 15)` |
| `not`    | Reverses the condition           | `not(a > 5)`        |

### **Examples**

```python
x = 10
y = 5

# AND operator
print(x > 5 and y > 3)   # True (both are True)

# OR operator
print(x > 5 or y > 10)   # True (one is True)

# NOT operator
print(not(x > 5))        # False (because x > 5 is True, and NOT makes it False)
```

---

## Combining All

Example:

```python
age = 18
has_id = True

if age >= 18 and has_id:
    print("Access Granted")
else:
    print("Access Denied")
```

Output:

```
Access Granted
```

---

### Key Takeaways

✔ Arithmetic operators handle math operations.  
✔ Comparison operators return True or False based on conditions.  
✔ Logical operators combine multiple conditions.

---
