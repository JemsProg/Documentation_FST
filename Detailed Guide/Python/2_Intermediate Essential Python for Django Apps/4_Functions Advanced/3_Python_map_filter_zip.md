# Python Basics: map(), filter(), and zip()

In this lesson, you’ll learn:

- What **map()**, **filter()**, and **zip()** functions do
- Why they are useful
- How to use them with examples

These functions make your code **shorter, cleaner, and more efficient** when working with iterables like lists.

---

## 1. map() Function

The `map()` function applies a **function to every item** in an iterable (like a list).

### **Syntax**

```python
map(function, iterable)
```

✔ Returns a **map object** (convert to list using `list()`).

### **Example**

```python
numbers = [1, 2, 3, 4]
squares = map(lambda x: x**2, numbers)
print(list(squares))  # [1, 4, 9, 16]
```

✔ Here:

- `lambda x: x**2` is applied to every number in the list.

---

## 2. filter() Function

The `filter()` function filters elements based on a **condition**.

### **Syntax**

```python
filter(function, iterable)
```

✔ The function should return **True** for items you want to keep.

### **Example**

```python
numbers = [10, 15, 20, 25]
evens = filter(lambda x: x % 2 == 0, numbers)
print(list(evens))  # [10, 20]
```

✔ Here:

- Only numbers divisible by 2 remain in the list.

---

## 3. zip() Function

The `zip()` function combines **two or more iterables** into **pairs** (tuples).

### **Syntax**

```python
zip(iterable1, iterable2, ...)
```

### **Example**

```python
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]

combined = zip(names, ages)
print(list(combined))  # [('Alice', 25), ('Bob', 30), ('Charlie', 35)]
```

✔ Useful for pairing related data like names and ages.

---

## 4. Using All Together

```python
names = ["Alice", "Bob", "Charlie"]
scores = [85, 92, 78]

# Increase each score by 5 using map
new_scores = list(map(lambda x: x + 5, scores))

# Filter names with score >= 90
passed = list(filter(lambda name_score: name_score[1] >= 90, zip(names, new_scores)))

print(passed)  # [('Bob', 97)]
```

---

### Key Takeaways

✔ **map()** → Apply a function to all elements.  
✔ **filter()** → Keep only elements that match a condition.  
✔ **zip()** → Combine multiple lists into pairs (or tuples).

---
