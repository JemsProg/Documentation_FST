# Python Basics: Special Methods (**str**, **repr**, **len**)

In this lesson, you’ll learn:

- What **special (dunder) methods** are in Python
- How to use `__str__`, `__repr__`, and `__len__`
- Why they are important in classes

These methods help make your **objects more readable and functional**.

---

## 1. What are Special (Dunder) Methods?

- Special methods in Python start and end with **double underscores** (e.g., `__init__`).
- They add **special behavior** to classes.
- Example: `__str__` controls what happens when you use `print(object)`.

✔ Commonly called **magic methods** or **dunder methods** (double underscore).

---

## 2. The **str** Method

- Defines the **string representation** of an object for humans.
- Called when you use `print()` or `str(object)`.

### **Example**

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"Name: {self.name}, Age: {self.age}"

p = Person("Alice", 25)
print(p)  # Name: Alice, Age: 25
```

✔ Without `__str__`, printing `p` would show something like:

```
<__main__.Person object at 0x...>
```

---

## 3. The **repr** Method

- Defines the **official string representation** of an object for developers.
- Called when you use `repr(object)` or type the object in the console.
- Should return a string that can **recreate the object** (when possible).

### **Example**

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __repr__(self):
        return f"Person('{self.name}', {self.age})"

p = Person("Bob", 30)
print(repr(p))  # Person('Bob', 30)
```

---

## 4. The **len** Method

- Defines what happens when you call `len(object)`.
- Commonly used for custom collections.

### **Example**

```python
class MyList:
    def __init__(self, items):
        self.items = items

    def __len__(self):
        return len(self.items)

my_list = MyList([1, 2, 3, 4])
print(len(my_list))  # 4
```

✔ You can now use `len()` on your custom object.

---

## 5. Why Use These Methods?

✔ Makes your objects **readable and user-friendly**.  
✔ Provides better debugging (`__repr__`).  
✔ Adds custom behavior (like `len()` for objects).

---

### Key Takeaways

✔ `__str__` → Human-readable string for print().  
✔ `__repr__` → Developer-friendly string for debugging.  
✔ `__len__` → Allows `len()` to work on your objects.

---
