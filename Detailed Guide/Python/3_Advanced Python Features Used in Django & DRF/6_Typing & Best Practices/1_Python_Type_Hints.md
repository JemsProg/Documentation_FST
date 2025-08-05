# Python Basics: Type Hints

In this lesson, you’ll learn:

- What **type hints** are
- Why they are useful
- How to use them in your Python programs

Type hints help make your code **clearer** and easier to **debug**, especially in large projects.

---

## 1. What are Type Hints?

- Type hints tell Python (and developers) what **type of data** a variable or function expects.
- They are **not enforced** by Python at runtime but help **documentation** and **code editors** provide suggestions and error checks.

✔ Type hints were introduced in **Python 3.5**.

---

## 2. Why Use Type Hints?

✔ Improves **code readability**.  
✔ Helps **IDEs and tools** detect type errors early.  
✔ Essential for **team projects** and **large codebases**.

---

## 3. Basic Syntax

You use `:` for variables and `->` for function return types.

### **Example**

```python
name: str = "Alice"
age: int = 25
price: float = 19.99
is_active: bool = True
```

✔ These hints show what type each variable should be.

---

## 4. Type Hints in Functions

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

print(greet("Alice"))
```

✔ `name: str` means the function expects a string.  
✔ `-> str` means the function will return a string.

---

## 5. Multiple Parameters

```python
def add(a: int, b: int) -> int:
    return a + b
```

---

## 6. Using Lists, Tuples, Dict

You can use `list`, `tuple`, and `dict` type hints:

```python
def get_names() -> list[str]:
    return ["Alice", "Bob"]

def get_person() -> dict[str, int]:
    return {"age": 30}
```

✔ Python 3.9+ allows this simpler syntax.

---

## 7. Using typing Module (Older Versions)

For older Python versions, use `typing`:

```python
from typing import List, Dict

def get_names() -> List[str]:
    return ["Alice", "Bob"]

def get_person() -> Dict[str, int]:
    return {"age": 30}
```

---

## 8. Optional and Union Types

✔ If a variable can have multiple types, use `|` (Python 3.10+):

```python
def get_age(age: int | None) -> str:
    return f"Age: {age if age else 'Unknown'}"
```

✔ Or use `Optional` (older versions):

```python
from typing import Optional
def get_age(age: Optional[int]) -> str:
    return f"Age: {age if age else 'Unknown'}"
```

---

## 9. Why is This Important for Django/DRF?

✔ Makes **API serializers**, **models**, and **views** easier to maintain.  
✔ Helps with **data validation** when using IDE tools.

---

### Key Takeaways

✔ Type hints **don’t enforce types at runtime**, but help detect errors early.  
✔ Use `:` for variables and `->` for function return types.  
✔ Use `typing` module for advanced hints (older Python versions).

---
