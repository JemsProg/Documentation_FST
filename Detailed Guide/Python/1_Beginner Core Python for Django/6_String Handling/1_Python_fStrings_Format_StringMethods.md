
#  Python Basics: f-strings, .format(), and String Methods

In this lesson, you’ll learn:
- How to format strings in Python
- The difference between **f-strings** and **.format()**
- Common string methods for text manipulation

These concepts are important for creating **dynamic text outputs** in your programs.

---

##  1. Why String Formatting?
String formatting lets you **insert variables into strings** instead of concatenating manually.

Example without formatting:
```python
name = "Alice"
age = 25
print("Name: " + name + ", Age: " + str(age))
```
This works but is **messy**.  
✔ Solution: Use f-strings or `.format()`.

---

##  2. Using f-strings (Recommended)
Introduced in Python 3.6, **f-strings** allow you to insert variables directly into strings.

### **Syntax**
```python
f"Text {variable}"
```

### **Example**
```python
name = "Alice"
age = 25
print(f"Hello, my name is {name} and I am {age} years old.")
```
Output:
```
Hello, my name is Alice and I am 25 years old.
```

✔ You can also perform **expressions** inside f-strings:
```python
print(f"Next year, I will be {age + 1}.")
```

---

##  3. Using .format() Method
Before f-strings, `.format()` was commonly used.

### **Example**
```python
name = "Bob"
age = 30
print("Hello, my name is {} and I am {} years old.".format(name, age))
```

✔ You can specify **positions**:
```python
print("Name: {0}, Age: {1}".format(name, age))
```

✔ Or use **named placeholders**:
```python
print("Name: {n}, Age: {a}".format(n="Charlie", a=28))
```

---

##  4. Common String Methods
String methods are functions that help you **modify or analyze strings**.

### **Examples**
```python
text = "  Hello World  "

# Change case
print(text.upper())     # "  HELLO WORLD  "
print(text.lower())     # "  hello world  "

# Remove spaces
print(text.strip())     # "Hello World"

# Count and find
print(text.count("l"))  # 3
print(text.find("World"))  # 8

# Replace text
print(text.replace("Hello", "Hi"))  # "  Hi World  "

# Check conditions
print(text.startswith("  H"))  # True
print(text.endswith("ld  "))   # True

# Split and join
words = text.strip().split(" ")  # ['Hello', 'World']
print("-".join(words))          # "Hello-World"
```

---

##  5. Combining f-strings with methods
You can use string methods **inside f-strings**:
```python
name = "alice"
print(f"Hello {name.upper()}!")  # Hello ALICE!
```

---

###  Key Takeaways
✔ Use **f-strings** for clean and readable string formatting.  
✔ `.format()` is an older but useful alternative.  
✔ Learn basic string methods like `.upper()`, `.lower()`, `.strip()`, `.replace()`.  

---

