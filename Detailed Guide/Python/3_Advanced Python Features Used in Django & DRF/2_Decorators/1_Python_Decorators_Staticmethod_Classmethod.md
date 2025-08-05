# Python Basics: Function Decorators (@staticmethod, @classmethod)

In this lesson, you’ll learn:

- What **decorators** are in Python
- The difference between `@staticmethod` and `@classmethod`
- When and how to use them in classes

Decorators modify the behavior of a function or method without changing its code.

---

## 1. What is a Decorator?

A **decorator** is a special function in Python that can change how another function works.  
In classes, we often use:

- `@staticmethod`
- `@classmethod`

These are **built-in decorators** that define how methods behave in relation to the class and its instances.

---

## 2. @staticmethod

A **static method**:

- Belongs to the class **but does NOT need access** to the class (`cls`) or instance (`self`).
- Works like a normal function, but is grouped inside a class for organization.

### **Syntax**

```python
@staticmethod
def method_name():
    # code
```

### **Example**

```python
class MathUtils:
    @staticmethod
    def add(a, b):
        return a + b

print(MathUtils.add(5, 3))  # 8
```

✔ You don’t need to create an object to call `add()`.

---

## 3. @classmethod

A **class method**:

- Belongs to the class.
- Takes `cls` as the first parameter (represents the class itself).
- Can **access and modify class variables**.

### **Syntax**

```python
@classmethod
def method_name(cls):
    # code
```

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

✔ Useful when you want to **change class-level data** for all objects.

---

## 4. Difference Between Them

| Feature         | @staticmethod     | @classmethod           |
| --------------- | ----------------- | ---------------------- |
| First Argument  | None              | `cls` (class itself)   |
| Access Instance | No                | No                     |
| Access Class    | No                | Yes                    |
| Use Case        | Utility functions | Modify class variables |

---

## 5. When to Use Each

✔ Use `@staticmethod` for helper functions that don’t need class data.  
✔ Use `@classmethod` when you need to work with class-level data.

---

### Key Takeaways

✔ `@staticmethod` → Independent function inside class.  
✔ `@classmethod` → Works with class-level data.  
✔ Both improve **code organization** in OOP.

---
