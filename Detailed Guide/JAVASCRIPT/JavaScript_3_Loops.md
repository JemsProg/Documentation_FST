# Loops and Iteration (JavaScript ES6)

Loops allow you to execute a block of code multiple times. They are essential for working with repetitive tasks like processing arrays or displaying data.

---

## **1. for Loop**

**Purpose:** Executes a block of code a specified number of times.

### Syntax:

```javascript
for (initialization; condition; increment) {
  // Code to execute
}
```

### Example:

```javascript
for (let i = 1; i <= 5; i++) {
  console.log("Number:", i);
}
```

**Output:** 1, 2, 3, 4, 5

**Where to Use:**

- Display a list of items
- Counting from 1 to N

---

## **2. while Loop**

**Purpose:** Executes a block of code **while a condition is true**.

### Syntax:

```javascript
while (condition) {
  // Code to execute
}
```

### Example:

```javascript
let i = 1;
while (i <= 3) {
  console.log("Loop count:", i);
  i++;
}
```

**Output:** 1, 2, 3

**Where to Use:**

- When you don't know how many times the loop should run

---

## **3. do...while Loop**

**Purpose:** Similar to `while`, but **executes at least once** before checking the condition.

### Syntax:

```javascript
do {
  // Code to execute
} while (condition);
```

### Example:

```javascript
let i = 1;
do {
  console.log("Executed:", i);
  i++;
} while (i <= 2);
```

**Output:** Executed: 1, Executed: 2

**Where to Use:**

- When you need the code to run at least once

---

## **4. for...in Loop**

**Purpose:** Iterates over the **properties (keys)** of an object.

### Syntax:

```javascript
for (let key in object) {
  // Access key and value
}
```

### Example:

```javascript
const user = { name: "Alice", age: 25 };
for (let key in user) {
  console.log(key, ":", user[key]);
}
```

**Output:**

```
name : Alice
age : 25
```

**Where to Use:**

- When you need to access object keys and values

---

## **5. for...of Loop**

**Purpose:** Iterates over the **values** of an iterable like arrays or strings.

### Syntax:

```javascript
for (let value of iterable) {
  // Access each value
}
```

### Example:

```javascript
const fruits = ["Apple", "Banana", "Cherry"];
for (let fruit of fruits) {
  console.log(fruit);
}
```

**Output:** Apple, Banana, Cherry

**Where to Use:**

- Looping through arrays, strings, or any iterable

---

### Best Practices:

- Use `for` for counting loops.
- Use `for...of` for arrays.
- Use `for...in` for objects.
- Avoid infinite loops by ensuring your condition will eventually be false.
