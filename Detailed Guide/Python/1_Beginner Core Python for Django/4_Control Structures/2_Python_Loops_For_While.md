# Python Basics: Loops (for and while)

Welcome! In this lesson, you’ll learn about **loops** in Python:

- **for loop** (Repeat actions for each item or range)
- **while loop** (Repeat actions while a condition is True)

Loops allow your program to **execute a block of code multiple times** without writing it repeatedly.

---

## 1. Why Use Loops?

Imagine printing numbers from 1 to 5:

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

This works, but it's inefficient. **Loops solve this by repeating code automatically.**

---

## 2. The for Loop

`for` loops are used to **iterate over a sequence** (like a list, tuple, string, or range).

### **Syntax**

```python
for variable in sequence:
    # Code to execute
```

### **Example: Using range()**

```python
for i in range(1, 6):
    print(i)
```

Output:

```
1
2
3
4
5
```

### **Example: Loop through a list**

```python
fruits = ["apple", "banana", "mango"]
for fruit in fruits:
    print(fruit)
```

Output:

```
apple
banana
mango
```

---

## 3. The while Loop

`while` loops run as long as a **condition is True**.

### **Syntax**

```python
while condition:
    # Code to execute
```

### **Example**

```python
count = 1
while count <= 5:
    print(count)
    count += 1
```

Output:

```
1
2
3
4
5
```

✔ **Important:** Avoid infinite loops! Always make sure the condition becomes False.

---

## 4. Loop Control Statements

Python provides ways to **control the flow inside loops**:

- `break` → Exit the loop completely
- `continue` → Skip the current iteration and move to the next

### **Example with break**

```python
for i in range(1, 10):
    if i == 5:
        break
    print(i)
```

Output:

```
1
2
3
4
```

### **Example with continue**

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

Output:

```
1
2
4
5
```

---

## 5. Nested Loops

You can use loops inside loops.

### **Example**

```python
for x in range(1, 3):
    for y in range(1, 3):
        print(f"x={x}, y={y}")
```

Output:

```
x=1, y=1
x=1, y=2
x=2, y=1
x=2, y=2
```

---

### Key Takeaways

✔ Use **for loops** for sequences or ranges.  
✔ Use **while loops** for conditions.  
✔ Control loops with **break** and **continue**.  
✔ Be careful with infinite loops in `while`.

---
