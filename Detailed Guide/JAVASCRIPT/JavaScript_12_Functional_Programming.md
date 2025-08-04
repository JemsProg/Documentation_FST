
#  Functional Programming & Advanced JavaScript

Functional programming is a programming paradigm in JavaScript that focuses on writing pure functions, avoiding shared state, and managing side effects.

---

## **1. Functional Programming**
**Definition:** A style of building software by composing functions, avoiding shared state, and side effects.

**Key Principles:**
- Use **pure functions**.
- Avoid **mutating data** (immutability).
- Use **higher-order functions**.

---

## **2. Pure Functions**
**Definition:** Functions that return the same output for the same input and do not modify external state.

### Example:
```javascript
function add(a, b) {
  return a + b; // Pure: no external dependencies
}
console.log(add(2, 3)); // 5
```

---

## **3. Immutability**
**Definition:** Data should not be changed after creation. Instead, create new copies when modifying.

### Example:
```javascript
const nums = [1, 2, 3];
const newNums = [...nums, 4]; // Instead of nums.push(4)
console.log(newNums); // [1, 2, 3, 4]
```

---

## **4. Higher-Order Functions**
**Definition:** Functions that take other functions as arguments or return functions.

### Example:
```javascript
function greet(fn) {
  fn();
}
greet(() => console.log("Hello!"));
```

---

## **5. Map, Filter, and Reduce**
These are higher-order functions commonly used in arrays.

### Examples:
```javascript
const nums = [1, 2, 3, 4];

// map: transform each element
const squares = nums.map(n => n * n); // [1, 4, 9, 16]

// filter: keep only even numbers
const evens = nums.filter(n => n % 2 === 0); // [2, 4]

// reduce: sum of all numbers
const sum = nums.reduce((acc, n) => acc + n, 0); // 10
```

---

## **6. Recursion**
**Definition:** A technique where a function calls itself to solve smaller parts of the same problem.

### Example:
```javascript
function factorial(n) {
  if (n === 1) return 1;
  return n * factorial(n - 1);
}
console.log(factorial(5)); // 120
```

---

## **7. Module Patterns**
**Definition:** Organizing code into reusable modules.

### Example (ES6 Modules):
```javascript
// math.js
export function add(a, b) {
  return a + b;
}

// main.js
import { add } from './math.js';
console.log(add(2, 3));
```

---

## **8. Singleton Pattern**
**Definition:** Ensures only one instance of a class exists.

### Example:
```javascript
class Singleton {
  constructor() {
    if (Singleton.instance) {
      return Singleton.instance;
    }
    Singleton.instance = this;
  }
}
const a = new Singleton();
const b = new Singleton();
console.log(a === b); // true
```

---

## **9. Observer Pattern**
**Definition:** An object (subject) maintains a list of observers and notifies them of state changes.

### Example:
```javascript
class Subject {
  constructor() {
    this.observers = [];
  }
  subscribe(observer) {
    this.observers.push(observer);
  }
  notify(data) {
    this.observers.forEach(observer => observer(data));
  }
}

const subject = new Subject();
subject.subscribe(data => console.log("Observer 1:", data));
subject.notify("Hello Observers!");
```

---

## **10. Promises & Async/Await Patterns**
**Definition:** For managing asynchronous operations.

### Example with async/await:
```javascript
async function fetchData() {
  const response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
  const data = await response.json();
  console.log(data);
}
fetchData();
```

---

## **11. Memoization**
**Definition:** Storing results of expensive function calls and returning cached results.

### Example:
```javascript
function memoize(fn) {
  const cache = {};
  return function(n) {
    if (cache[n]) return cache[n];
    const result = fn(n);
    cache[n] = result;
    return result;
  };
}

const square = memoize(n => n * n);
console.log(square(4)); // Computed
console.log(square(4)); // Cached
```

---

### Best Practices:
- Use **pure functions** to make code predictable.
- Prefer **map, filter, reduce** over loops for clarity.
- Use **memoization** for performance optimization.
