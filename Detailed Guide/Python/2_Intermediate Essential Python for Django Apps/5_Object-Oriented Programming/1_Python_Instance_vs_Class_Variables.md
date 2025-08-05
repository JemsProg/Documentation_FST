# Python Basics: Instance vs Class Variables

In this lesson, you’ll learn:

- What **instance variables** are
- What **class variables** are
- How they are different and when to use them

Understanding this concept is important for **Object-Oriented Programming** and frameworks like Django.

---

## 1. What is an Instance Variable?

- An **instance variable** belongs to a specific object (instance of a class).
- Defined inside the `__init__()` method using `self`.
- **Each object has its own copy** of the instance variable.

### **Example**

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand      # Instance variable
        self.color = color      # Instance variable

car1 = Car("Toyota", "Red")
car2 = Car("Honda", "Blue")

print(car1.brand)  # Toyota
print(car2.brand)  # Honda
```

✔ Here:

- `brand` and `color` are **instance variables**.
- Changing `car1.brand` does **not** affect `car2.brand`.

---

## 2. What is a Class Variable?

- A **class variable** is shared by **all objects** of the class.
- Defined **inside the class but outside any method**.
- Useful for values that should be the same for every object.

### **Example**

```python
class Car:
    wheels = 4  # Class variable

    def __init__(self, brand):
        self.brand = brand  # Instance variable

car1 = Car("Toyota")
car2 = Car("Honda")

print(car1.wheels)  # 4
print(car2.wheels)  # 4
```

✔ Both `car1` and `car2` share the **same class variable** `wheels`.

---

## 3. Changing Values

- **Instance variables** can be changed per object.
- **Class variables** change for **all objects** if modified at the class level.

### **Example**

```python
Car.wheels = 6  # Change class variable
print(car1.wheels)  # 6
print(car2.wheels)  # 6

car1.brand = "Ford"  # Change instance variable
print(car1.brand)  # Ford
print(car2.brand)  # Honda
```

---

## 4. When to Use

✔ Use **instance variables** for data specific to each object (e.g., brand, color).  
✔ Use **class variables** for properties common to all objects (e.g., number of wheels).

---

### Key Differences Table

| Feature            | Instance Variable   | Class Variable                          |
| ------------------ | ------------------- | --------------------------------------- |
| **Belongs to**     | Individual object   | Class (shared by all)                   |
| **Defined in**     | `__init__()` method | Inside class, outside methods           |
| **Changes affect** | Only that object    | All objects (if changed at class level) |

---

### Key Takeaways

✔ Instance variables → Unique per object.  
✔ Class variables → Shared by all objects.  
✔ Useful for organizing data in OOP programs.

---
