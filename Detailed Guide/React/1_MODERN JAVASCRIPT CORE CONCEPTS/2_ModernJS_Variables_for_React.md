# Modern JavaScript for React: Variables

Before learning React, you must understand how to work with **variables** in JavaScript because React heavily relies on them for storing and managing data.

---

## **What Are Variables?**

Variables are **containers for storing data** in a program. In JavaScript (ES6 and beyond), there are **three main ways** to declare variables:

- **var** – Old way (avoid using it)
- **let** – For values that can change
- **const** – For values that should not change

---

## **1. var (Old and Avoid)**

`var` was used in older JavaScript, but it has issues like **function scope** and **hoisting problems**, so modern code avoids it.

Example:

```javascript
var name = "John";
console.log(name); // John
```

**Why avoid `var`?**

- It can be re-declared accidentally, causing bugs.
- It does not respect **block scope**.

---

## **2. let (Preferred for Changeable Values)**

`let` allows you to declare a variable that **can be reassigned later**.

Example:

```javascript
let age = 25;
age = 26; //  Allowed
console.log(age); // 26
```

**Where to use?**

- When you need to **update a value later**, like counters, form input values, etc.

---

## **3. const (Preferred for Fixed Values)**

`const` creates a variable that **cannot be reassigned**.

Example:

```javascript
const country = "Philippines";
// country = "USA"; ❌ Error: Assignment to constant variable
console.log(country);
```

**Where to use?**

- When the value should **never change**, like API URLs or configuration.

---

## **Best Practices**

- **Always prefer `const`** by default.
- Use `let` only when you know the value will change.
- **Never use `var`** in modern JavaScript.

---

## Example in React

React often uses `const` when creating **components**, because components don't need to change:

```javascript
const App = () => {
  return <h1>Hello, React!</h1>;
};
export default App;
```

For values that **change**, like user input, React uses **state** (with `useState`), which internally works like variables.

---

### Summary

- Use `const` for constants and functions.
- Use `let` for variables that will be reassigned.
- Avoid `var` completely.

---
