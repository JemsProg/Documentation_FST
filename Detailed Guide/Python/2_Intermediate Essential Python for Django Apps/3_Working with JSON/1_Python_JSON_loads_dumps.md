# Python Basics: json.loads() and json.dumps()

In this lesson, you’ll learn:

- What JSON is
- How to use **json.loads()** and **json.dumps()**
- Why these are important for APIs and Django REST Framework

---

## 1. What is JSON?

**JSON** (JavaScript Object Notation) is a lightweight data format used for:
✔ Data exchange between client and server  
✔ APIs and web services

Example of JSON data:

```json
{
  "name": "Alice",
  "age": 25,
  "is_student": true
}
```

In Python:

- JSON **strings** need to be converted to **Python objects** for use.
- Python **objects** need to be converted to **JSON strings** for sending to APIs.

---

## 2. Importing the json Module

```python
import json
```

---

## 3. json.loads() → JSON String to Python Object

The `json.loads()` function converts a JSON **string** into a **Python dictionary**.

### **Example**

```python
import json

# JSON string
json_data = '{"name": "Alice", "age": 25, "is_student": true}'

# Convert to Python dictionary
python_data = json.loads(json_data)

print(python_data)            # {'name': 'Alice', 'age': 25, 'is_student': True}
print(type(python_data))      # <class 'dict'>
print(python_data["name"])    # Alice
```

✔ This is important when receiving **API responses**.

---

## 4. json.dumps() → Python Object to JSON String

The `json.dumps()` function converts a **Python dictionary** into a JSON **string**.

### **Example**

```python
import json

# Python dictionary
data = {"name": "Bob", "age": 30, "is_student": False}

# Convert to JSON string
json_string = json.dumps(data)

print(json_string)        # {"name": "Bob", "age": 30, "is_student": false}
print(type(json_string))  # <class 'str'>
```

✔ This is important when **sending data to APIs**.

---

## 5. Formatting JSON Output

You can make JSON output pretty using `indent`:

```python
print(json.dumps(data, indent=4))
```

Output:

```json
{
  "name": "Bob",
  "age": 30,
  "is_student": false
}
```

---

## 6. Why is This Important for APIs?

✔ APIs use JSON for **data exchange**.  
✔ Django REST Framework sends and receives **JSON data**.  
✔ You need to **convert between JSON and Python objects** often.

---

### Key Takeaways

✔ `json.loads()` → JSON string → Python dictionary  
✔ `json.dumps()` → Python dictionary → JSON string  
✔ Use `indent` for readable output

---
