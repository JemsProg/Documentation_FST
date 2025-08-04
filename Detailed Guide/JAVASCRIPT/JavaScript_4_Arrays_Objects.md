# Arrays and Objects (JavaScript ES6)

Arrays and Objects are **fundamental data structures** in JavaScript. They allow you to store, organize, and manipulate collections of data.

---

## **1. Arrays**

**Definition:** Arrays are ordered collections of values, accessed by **numeric indices** starting from 0.

### Syntax:

```javascript
const fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits[0]); // Apple
```

**Where to Use:**

- Lists of items like products, users, scores.

---

### **Common Array Methods**

These are built-in functions to manipulate arrays:

| Method      | Description                            |
| ----------- | -------------------------------------- |
| `push()`    | Adds an item at the **end**            |
| `pop()`     | Removes the **last** item              |
| `shift()`   | Removes the **first** item             |
| `unshift()` | Adds an item at the **beginning**      |
| `splice()`  | Adds/removes items at a specific index |
| `slice()`   | Returns a portion of an array          |

### Examples:

```javascript
const fruits = ["Apple", "Banana"];

// Add items
fruits.push("Cherry"); // ["Apple", "Banana", "Cherry"]
fruits.unshift("Mango"); // ["Mango", "Apple", "Banana", "Cherry"]

// Remove items
fruits.pop(); // Removes "Cherry"
fruits.shift(); // Removes "Mango"

// Extract part of an array
const newFruits = fruits.slice(0, 2); // ["Apple", "Banana"]
```

**Real Use Case:**

- Shopping cart items
- Storing user inputs in a quiz

---

## **2. Objects**

**Definition:** Objects store **key-value pairs**, where values are accessed by keys instead of indices.

### Syntax:

```javascript
const user = {
  name: "Alice",
  age: 25,
  isAdmin: true,
};
console.log(user.name); // Alice
```

**Where to Use:**

- Representing a single entity (like a user, product, or settings).

---

### **Accessing Object Values**

- Dot notation: `user.name`
- Bracket notation: `user["age"]`

### Example:

```javascript
console.log(user.name); // Alice
console.log(user["isAdmin"]); // true
```

---

### **Modifying Object Properties**

```javascript
user.age = 30; // Update value
user.email = "alice@example.com"; // Add new property
delete user.isAdmin; // Remove property
```

---

## **3. Object Methods**

Objects can also have functions as properties (called **methods**).

### Example:

```javascript
const user = {
  name: "Alice",
  greet() {
    console.log(`Hello, ${this.name}`);
  },
};

user.greet(); // Hello, Alice
```

**Real Use Case:**

- Objects with behavior, like a user profile or a product with actions.

---

### Best Practices:

- Use **arrays** for ordered lists of similar items.
- Use **objects** for structured data representing entities.
- Combine both when necessary (e.g., an array of objects for a list of users).

---

## Complete Example:

```javascript
const users = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 30 },
];

// Loop through users
users.forEach((user) => console.log(user.name));
```

**Output:** Alice, Bob
