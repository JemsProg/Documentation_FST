# React Concept: Purity

**Purity** in React refers to writing **pure functions** for your components.  
A **pure function** always returns the same output for the same input and has **no side effects**.

---

## **1. What is a Pure Function?**

A function is **pure** if:

- It does **not modify external variables or state**.
- It does **not produce side effects** (like changing the DOM, making API calls inside the function).
- It **returns the same output given the same input**.

### Example of a Pure Function

```javascript
function add(a, b) {
  return a + b; // ✅ Always gives the same result for same inputs
}
console.log(add(2, 3)); // 5
```

### Impure Function Example

```javascript
let total = 0;
function addToTotal(num) {
  total += num; // ❌ Changes external variable
  return total;
}
```

---

## **2. Why Purity Matters in React**

React components should behave like **pure functions of props and state**:

- For the same **props and state**, a component should render the same UI.
- This makes apps **predictable and easy to debug**.

---

## **3. Pure React Component Example**

```javascript
const Greeting = ({ name }) => {
  return <h1>Hello, {name}!</h1>; // ✅ Pure: Output depends only on props
};
```

### Impure Component Example

```javascript
const Greeting = ({ name }) => {
  console.log("Rendering..."); // ❌ Side effect in render
  return <h1>Hello, {name}!</h1>;
};
```

---

## **Where Side Effects Should Go**

- Side effects (like API calls, DOM changes) should **not be in render()**.
- React provides **hooks like useEffect** for side effects.

Example:

```javascript
import React, { useEffect } from "react";

const App = () => {
  useEffect(() => {
    console.log("API call or DOM update happens here"); // ✅ Allowed in useEffect
  }, []);

  return <h1>Hello, React!</h1>;
};
```

---

### Summary

✔ React components should be **pure functions** of props and state.  
✔ No side effects in **rendering logic**.  
✔ Use `useEffect` for side effects (API calls, subscriptions).

---
