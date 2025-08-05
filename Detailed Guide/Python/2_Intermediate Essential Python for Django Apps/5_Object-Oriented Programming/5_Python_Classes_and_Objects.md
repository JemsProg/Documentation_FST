# Python Basics: Classes and Objects

In this lesson, you’ll learn:

- What **classes** and **objects** are
- How to create classes in Python
- How to use objects to store and manage data

Understanding **OOP (Object-Oriented Programming)** is essential for Django and Django REST Framework.

---

## 1. What is a Class?

A **class** is a blueprint for creating objects.  
It defines **attributes (variables)** and **methods (functions)** that an object will have.

Example in real life:

- **Class**: Car (blueprint)
- **Objects**: Toyota, Honda, BMW (real cars)

---

## 2. What is an Object?

An **object** is an **instance of a class**.  
You create objects from a class to **use its attributes and methods**.

---

## 3. Creating a Simple Class

### **Syntax**

```python
class ClassName:
    # attributes and methods
```

### **Example**

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

# Create an object (instance of Car)
my_car = Car("Toyota", "Red")
print(my_car.brand)  # Toyota
print(my_car.color)  # Red
```

✔ `__init__` is a **special method** called a **constructor**.  
✔ It runs automatically when you create an object.  
✔ `self` refers to the **current object**.

---

## 4. Adding Methods

A **method** is a function inside a class that belongs to an object.

### **Example**

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

    def show_details(self):
        print(f"Brand: {self.brand}, Color: {self.color}")

my_car = Car("Honda", "Blue")
my_car.show_details()
```

Output:

```
Brand: Honda, Color: Blue
```

---

## 5. Why Use Classes?

✔ Organizes code into reusable components.  
✔ Helps manage **real-world entities** in programs.  
✔ Essential for **Django models, views, and serializers**.

---

## 6. Multiple Objects from Same Class

```python
car1 = Car("Toyota", "White")
car2 = Car("Ford", "Black")

car1.show_details()
car2.show_details()
```

---

## 7. Attributes and Methods Summary

- **Attributes** = Variables inside a class (`self.brand`)
- **Methods** = Functions inside a class (`def show_details()`)

---

### Key Takeaways

✔ A **class** is a blueprint; an **object** is an instance.  
✔ Use `__init__` to initialize object attributes.  
✔ Use `self` to access instance variables and methods.

---
