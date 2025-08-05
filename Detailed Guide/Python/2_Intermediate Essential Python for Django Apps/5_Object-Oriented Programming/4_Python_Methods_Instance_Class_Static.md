# Python Basics: Methods in Classes (Instance, Class, and Static)

In this lesson, you’ll learn:

- What **methods** are in classes
- The difference between **Instance**, **Class**, and **Static** methods
- How to use them with examples

Methods are **functions inside a class** that define the behavior of objects.

---

## 1. What are Methods?

- A **method** is a function defined inside a class.
- They operate on **object data** or **class data**.

There are **three types** of methods in Python:

1. **Instance Methods** → Work with individual objects
2. **Class Methods** → Work with the class as a whole
3. **Static Methods** → Independent of class or instance data

---

## 2. Instance Methods

- The most common type of method.
- Defined with `self` as the first parameter.
- Can access and modify **instance variables**.

### **Example**

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

    def show_details(self):  # Instance method
        print(f"Brand: {self.brand}, Color: {self.color}")

car1 = Car("Toyota", "Red")
car1.show_details()
```

Output:

```
Brand: Toyota, Color: Red
```

---

## 3. Class Methods

- Defined using the `@classmethod` decorator.
- First parameter is `cls` (refers to the class, not the object).
- Can **modify class variables**.

### **Example**

```python
class Car:
    wheels = 4  # Class variable

    @classmethod
    def change_wheels(cls, count):
        cls.wheels = count

Car.change_wheels(6)
print(Car.wheels)  # 6
```

✔ Use class methods when you need to **work with class-level data**.

---

## 4. Static Methods

- Defined using the `@staticmethod` decorator.
- **Do not take self or cls** as the first parameter.
- Behave like normal functions but live inside a class for **organization**.

### **Example**

```python
class MathUtils:
    @staticmethod
    def add(a, b):
        return a + b

print(MathUtils.add(5, 3))  # 8
```

✔ Use static methods when the logic is related to the class but doesn’t need access to class or instance data.

---

## Summary Table

| Method Type  | First Parameter | Can Access         | Use Case                 |
| ------------ | --------------- | ------------------ | ------------------------ |
| **Instance** | `self`          | Instance variables | Object-specific behavior |
| **Class**    | `cls`           | Class variables    | Modify class-level data  |
| **Static**   | None            | Neither            | Utility functions        |

---

### Key Takeaways

✔ **Instance methods** → Work with object data.  
✔ **Class methods** → Work with class data.  
✔ **Static methods** → Independent functions inside a class.

---
