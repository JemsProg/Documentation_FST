# Python Basics: The **init**() Method

In this lesson, you’ll learn:

- What the `__init__()` method is
- Why it’s important in Python classes
- How to use it with examples

The `__init__()` method is **crucial** for creating classes and objects in Python.

---

## 1. What is the **init**() Method?

The `__init__()` method is a **special method** in Python classes.  
It is called **automatically** when you create an object from a class.

✔ It is also known as the **constructor**.  
✔ Used to **initialize object attributes**.

---

## 2. Syntax

```python
class ClassName:
    def __init__(self, parameters):
        # initialize attributes
```

✔ The first parameter is always `self` (represents the object itself).  
✔ You can add more parameters for object attributes.

---

## 3. Simple Example

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

# Creating an object calls __init__() automatically
person1 = Person("Alice", 25)
print(person1.name)  # Alice
print(person1.age)   # 25
```

✔ `self.name = name` → Assigns the value of `name` to the object's attribute.  
✔ Each object can have **different values** for these attributes.

---

## 4. Why Do We Need **init**()?

Without `__init__()`, we would need to manually set attributes after creating an object:

```python
class Person:
    pass

p = Person()
p.name = "Alice"
p.age = 25
```

✔ `__init__()` makes this process **automatic** and **organized**.

---

## 5. Adding Default Values

You can set default values for parameters.

```python
class Person:
    def __init__(self, name="Guest", age=18):
        self.name = name
        self.age = age

p1 = Person()                # Uses default values
p2 = Person("Bob", 30)       # Overrides defaults

print(p1.name, p1.age)  # Guest 18
print(p2.name, p2.age)  # Bob 30
```

---

## 6. Adding Methods with **init**()

You can define other methods to work with attributes.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print(f"My name is {self.name}, and I am {self.age} years old.")

p = Person("Charlie", 22)
p.introduce()
```

Output:

```
My name is Charlie, and I am 22 years old.
```

---

### Key Takeaways

✔ `__init__()` runs **automatically** when creating an object.  
✔ It initializes attributes for each object.  
✔ Always include `self` as the first parameter.  
✔ You can set **default values** in `__init__()`.

---
