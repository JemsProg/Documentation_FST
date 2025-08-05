# Python Basics: if, elif, else Statements

Welcome! In this lesson, you’ll learn about **conditional statements** in Python:

- **if** (Check a condition)
- **elif** (Check another condition if previous ones are False)
- **else** (Run when all conditions are False)

These statements control the **flow of your program** based on conditions.

---

## 1. What is a Conditional Statement?

A conditional statement allows your program to **make decisions**.  
Example: If a user is 18 or older, allow them to vote.

---

## 2. The if Statement

The `if` statement checks a condition. If it’s **True**, the code inside runs.

### **Syntax**

```python
if condition:
    # Code to run if condition is True
```

### **Example**

```python
age = 20
if age >= 18:
    print("You can vote!")
```

Output:

```
You can vote!
```

---

## 3. The else Statement

`else` runs if **none of the if or elif conditions are True**.

### **Example**

```python
age = 15
if age >= 18:
    print("You can vote!")
else:
    print("You are too young to vote.")
```

Output:

```
You are too young to vote.
```

---

## 4. The elif Statement

`elif` stands for **else if**. It checks another condition if the first one is False.

### **Example**

```python
marks = 75
if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")
else:
    print("Grade C")
```

Output:

```
Grade B
```

✔ You can have **multiple elif statements**.

---

## 5. Combining Conditions

You can use **logical operators** (`and`, `or`, `not`) with if conditions.

### **Example**

```python
age = 20
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

## 6. Nested if Statements

You can put an `if` inside another `if`.

### **Example**

```python
age = 20
if age >= 18:
    if age >= 21:
        print("You can drink and vote.")
    else:
        print("You can vote, but not drink.")
```

Output:

```
You can vote, but not drink.
```

---

### Key Takeaways

✔ Use **if** to check a condition.  
✔ Use **elif** for extra conditions.  
✔ Use **else** for the default case.  
✔ Indentation matters in Python!

---
