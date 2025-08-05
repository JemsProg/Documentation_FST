# Python Basics: Strings, Integers, Floats, and Booleans

Welcome! In this lesson, you’ll learn about **four important data types in Python**:

- **Strings** (Text data)
- **Integers** (Whole numbers)
- **Floats** (Decimal numbers)
- **Booleans** (True or False values)

These are fundamental for storing and manipulating data in your programs.

---

## 1. Strings (Text Data)

A **string** is a sequence of characters enclosed in quotes.

### **How to create a string**

```python
name = "Alice"
greeting = 'Hello'
sentence = """This is a multi-line string."""
```

### **String operations**

```python
# Concatenation
first_name = "Alice"
last_name = "Smith"
full_name = first_name + " " + last_name  # "Alice Smith"

# Repetition
laugh = "Ha" * 3  # "HaHaHa"

# Access characters
word = "Python"
print(word[0])  # 'P' (index starts at 0)
```

### **Useful string methods**

```python
text = " hello world "
print(text.upper())     # " HELLO WORLD "
print(text.lower())     # " hello world "
print(text.strip())     # "hello world" (removes spaces)
print(len(text))        # 13 (length of string)
```

---

## 2. Integers (Whole Numbers)

An **integer** is a number without a decimal point.

### **Examples**

```python
age = 25
year = 2025
```

### **Operations with integers**

```python
x = 10
y = 3
print(x + y)   # 13
print(x - y)   # 7
print(x * y)   # 30
print(x // y)  # 3 (integer division)
print(x % y)   # 1 (modulus)
```

---

## 3. Floats (Decimal Numbers)

A **float** represents numbers with decimals.

### **Examples**

```python
price = 19.99
average = 4.5
```

### **Operations with floats**

```python
x = 5.5
y = 2.0
print(x / y)  # 2.75
print(x * y)  # 11.0
```

✔ Note: Combining int + float results in a float:

```python
result = 5 + 2.5  # 7.5
```

---

## 4. Booleans (True or False)

A **Boolean** is a data type with only two values:

- `True`
- `False`

### **Examples**

```python
is_active = True
is_logged_in = False
```

### **Using Booleans in conditions**

```python
age = 18
print(age >= 18)  # True
print(age < 18)   # False
```

✔ Booleans are often used in `if` statements.

---

## Type Checking

Use `type()` to check the type of a variable:

```python
name = "Alice"
age = 25
price = 19.99
is_student = True

print(type(name))       # <class 'str'>
print(type(age))        # <class 'int'>
print(type(price))      # <class 'float'>
print(type(is_student)) # <class 'bool'>
```

---

### Key Takeaways

✔ **String** = Text in quotes  
✔ **Integer** = Whole number  
✔ **Float** = Decimal number  
✔ **Boolean** = `True` or `False`  
✔ Use `type()` to check the data type.

---
