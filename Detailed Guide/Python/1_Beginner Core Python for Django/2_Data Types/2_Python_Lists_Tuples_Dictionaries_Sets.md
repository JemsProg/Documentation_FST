# Python Basics: Lists, Tuples, Dictionaries, and Sets

Welcome! In this lesson, you’ll learn about **four important data structures in Python**:

- **Lists** (Ordered, changeable collections)
- **Tuples** (Ordered, unchangeable collections)
- **Dictionaries** (Key-value pairs)
- **Sets** (Unordered, unique elements)

These are essential for organizing and managing data in your Python programs.

---

## 1. Lists

A **list** is an ordered collection that can hold multiple values. Lists are **mutable** (you can change them).

### **Create a list**

```python
fruits = ["apple", "banana", "cherry"]
```

### **Access elements**

```python
print(fruits[0])   # "apple"
print(fruits[-1])  # "cherry" (last element)
```

### **Modify elements**

```python
fruits[1] = "mango"
print(fruits)  # ["apple", "mango", "cherry"]
```

### **Common list methods**

```python
fruits.append("orange")   # Add at the end
fruits.insert(1, "grape") # Add at specific position
fruits.remove("apple")    # Remove an item
print(len(fruits))        # Get length of list
```

---

## 2. Tuples

A **tuple** is like a list, but **immutable** (cannot be changed after creation).

### **Create a tuple**

```python
colors = ("red", "green", "blue")
```

### **Access elements**

```python
print(colors[0])   # "red"
```

✔ Tuples are useful for fixed data like coordinates:

```python
point = (10, 20)
```

---

## 3. Dictionaries

A **dictionary** stores data in **key-value pairs**.

### **Create a dictionary**

```python
person = {
    "name": "Alice",
    "age": 25,
    "city": "New York"
}
```

### **Access values by key**

```python
print(person["name"])   # "Alice"
```

### **Modify values**

```python
person["age"] = 26
person["email"] = "alice@example.com"  # Add new key-value
```

### **Common dictionary methods**

```python
print(person.keys())    # dict_keys(['name', 'age', 'city', 'email'])
print(person.values())  # dict_values([...])
```

---

## 4. Sets

A **set** is an unordered collection with **unique elements** (no duplicates).

### **Create a set**

```python
numbers = {1, 2, 3, 3, 4}
print(numbers)  # {1, 2, 3, 4} (duplicates removed)
```

### **Add and remove elements**

```python
numbers.add(5)
numbers.remove(2)
```

✔ Useful for eliminating duplicates from a list:

```python
unique = set([1, 2, 2, 3])
print(unique)  # {1, 2, 3}
```

---

## Summary Table

| Type      | Ordered | Mutable | Allows Duplicates | Example          |
| --------- | ------- | ------- | ----------------- | ---------------- |
| **List**  | Yes     | Yes     | Yes               | [1, 2, 3]        |
| **Tuple** | Yes     | No      | Yes               | (1, 2, 3)        |
| **Dict**  | No\*    | Yes     | Keys unique       | {"a": 1, "b": 2} |
| **Set**   | No      | Yes     | No                | {1, 2, 3}        |

\*Dictionaries maintain insertion order in Python 3.7+.

---

### Key Takeaways

✔ **Lists** → Changeable, ordered collections  
✔ **Tuples** → Unchangeable, ordered collections  
✔ **Dictionaries** → Key-value pairs  
✔ **Sets** → Unique, unordered elements

---
