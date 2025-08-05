# Python Basics: The yield Keyword

In this lesson, you’ll learn:

- What the **yield** keyword is
- How it differs from **return**
- Why and when to use yield in your Python programs

The `yield` keyword is used to **create generators** in Python, which are very useful for handling large data efficiently.

---

## 1. What is yield?

- `yield` is like `return` but instead of ending the function, it **pauses the function and saves its state**.
- When the function is called again, it resumes from where it left off.
- A function that contains `yield` becomes a **generator function**.

---

## 2. Why Use yield?

✔ To **save memory** when working with large data (does not store all values in memory).  
✔ To **generate values one at a time** instead of all at once.

---

## 3. Example: Using return vs yield

### Using return:

```python
def get_numbers():
    return [1, 2, 3]

print(get_numbers())  # [1, 2, 3]
```

✔ This returns the entire list at once.

---

### Using yield:

```python
def generate_numbers():
    yield 1
    yield 2
    yield 3

for num in generate_numbers():
    print(num)
```

Output:

```
1
2
3
```

✔ `yield` allows you to **iterate** over values one by one.

---

## 4. Generator with a Loop

You can use `yield` in a loop to generate many values efficiently.

```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1

for num in countdown(5):
    print(num)
```

Output:

```
5
4
3
2
1
```

---

## 5. Difference Between return and yield

| Feature  | return                      | yield                          |
| -------- | --------------------------- | ------------------------------ |
| Behavior | Ends the function           | Pauses function, resumes later |
| Memory   | Stores all values in memory | Generates values one by one    |
| Use Case | Small data sets             | Large or infinite sequences    |

---

## 6. Real-Life Use of yield

✔ Reading **large files line by line**.  
✔ Streaming **data in APIs**.  
✔ Creating **infinite sequences** without using too much memory.

---

### Key Takeaways

✔ `yield` turns a function into a **generator**.  
✔ It produces values **lazily** (one at a time).  
✔ Use it for **efficient memory usage** in large or infinite data sets.

---
