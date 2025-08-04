
#  Modern JavaScript for React: ES Modules (Import & Export)

Modules in JavaScript allow you to **split your code into smaller, reusable files**.  
React heavily relies on ES Modules for **organizing components** and **sharing logic**.

---

## **1. What Are ES Modules?**
- Introduced in **ES6**.
- A **module** is a file that contains code (functions, classes, variables) that can be **imported** or **exported** to other files.
- Helps in **keeping code clean and maintainable**.

---

## **2. Exporting in JavaScript**
There are **two types of exports**:  
- **Named Export**
- **Default Export**

###  **Named Export**
Export multiple values from a file:
```javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

Importing named exports:
```javascript
import { add, subtract } from "./math.js";
console.log(add(2, 3)); // 5
```

---

###  **Default Export**
Export only one default value from a file:
```javascript
// greet.js
export default function greet(name) {
  return `Hello, ${name}!`;
}
```

Importing a default export:
```javascript
import greet from "./greet.js";
console.log(greet("Alice")); // Hello, Alice!
```

---

## **3. Combining Named and Default Exports**
```javascript
// utils.js
export const multiply = (a, b) => a * b;
export default function greet(name) {
  return `Hi, ${name}`;
}
```

Importing:
```javascript
import greet, { multiply } from "./utils.js";
console.log(greet("Alice")); // Hi, Alice
console.log(multiply(3, 4)); // 12
```

---

##  **ES Modules in React**
React uses modules to organize components:
```javascript
// Header.js
const Header = () => {
  return <h1>My App Header</h1>;
};
export default Header;
```

Importing the component in **App.js**:
```javascript
import Header from "./Header";
function App() {
  return (
    <div>
      <Header />
      <p>Welcome to React!</p>
    </div>
  );
}
export default App;
```

---

###  Summary
✔ Use **`export` and `import`** to share code across files.  
✔ **Default Export** → for a single main function/class/component.  
✔ **Named Export** → for multiple utilities from the same file.  
✔ React uses **ES Modules** to organize components.

---
