# Python Basics: Inheritance & Polymorphism

In this lesson, you’ll learn:

- What **Inheritance** is and why it’s important
- What **Polymorphism** is and how to use it
- Examples of both concepts in Python

These concepts are **core principles of Object-Oriented Programming (OOP)** and are widely used in Django and Django REST Framework.

---

## 1. What is Inheritance?

**Inheritance** allows a class (**child**) to reuse the properties and methods of another class (**parent**).

✔ It helps in **code reusability** and **organization**.

### **Syntax**

```python
class ParentClass:
    # parent code

class ChildClass(ParentClass):
    # child code
```

---

## 2. Example of Inheritance

```python
class Animal:
    def speak(self):
        print("This animal makes a sound")

class Dog(Animal):
    def bark(self):
        print("Woof! Woof!")

dog = Dog()
dog.speak()  # Inherited from Animal
dog.bark()   # Defined in Dog
```

✔ Here:

- `Dog` inherits from `Animal`.
- `Dog` can use both its own methods and the parent’s methods.

---

## 3. The **init**() Method in Inheritance

When a child class needs its own constructor, you can still call the **parent constructor** using `super()`.

### **Example**

```python
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)  # Call parent constructor
        self.breed = breed

dog = Dog("Buddy", "Labrador")
print(dog.name, dog.breed)
```

Output:

```
Buddy Labrador
```

---

## 4. Types of Inheritance

✔ **Single Inheritance** → One parent, one child.  
✔ **Multiple Inheritance** → Child inherits from multiple parents.  
✔ **Multilevel Inheritance** → A chain of inheritance.

---

## 5. What is Polymorphism?

**Polymorphism** means **same method name, different behavior** depending on the object.

✔ In Python, it is often implemented by **method overriding**.

---

## 6. Example of Polymorphism

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def speak(self):
        print("Dog barks")

class Cat(Animal):
    def speak(self):
        print("Cat meows")

animals = [Dog(), Cat()]

for animal in animals:
    animal.speak()
```

Output:

```
Dog barks
Cat meows
```

✔ Here, `speak()` behaves differently for `Dog` and `Cat`.

---

## 7. Why Use Inheritance & Polymorphism?

✔ Avoid code duplication.  
✔ Make programs **scalable** and **maintainable**.  
✔ Used in **Django Models and Views** extensively.

---

### Key Takeaways

✔ **Inheritance** → Share code between classes.  
✔ **Polymorphism** → Same method name, different behaviors.  
✔ Use `super()` to call the parent constructor.

---
