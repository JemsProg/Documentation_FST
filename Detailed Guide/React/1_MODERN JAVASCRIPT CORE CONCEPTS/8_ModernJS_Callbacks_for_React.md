# Modern JavaScript for React: Callbacks

A **callback function** is a function that is passed as an argument to another function and executed later.  
Callbacks are widely used in JavaScript and React for **handling asynchronous operations**, **event handling**, and **passing functions as props**.

---

## **1. What is a Callback?**

- A callback is simply **a function passed as an argument to another function**.
- The receiving function can call it later (hence the name "callback").

---

### ✅ Example: Basic Callback

```javascript
function greet(name, callback) {
  console.log(`Hello, ${name}`);
  callback();
}

function sayBye() {
  console.log("Goodbye!");
}

greet("Alice", sayBye);
// Output:
// Hello, Alice
// Goodbye!
```

**Explanation:**

- `sayBye` is passed as a callback to `greet`.
- `greet` calls `sayBye()` after greeting.

---

## **2. Callbacks in Asynchronous Code**

JavaScript uses callbacks for **async operations** like API calls, setTimeout, etc.

```javascript
console.log("Start");

setTimeout(() => {
  console.log("This runs after 2 seconds");
}, 2000);

console.log("End");
// Output:
// Start
// End
// This runs after 2 seconds
```

**Why use callbacks?**

- They allow code to **continue running** without waiting for time-consuming tasks.

---

## **Callbacks in React**

React uses callbacks in **event handlers** and when **passing functions as props**.

### Example: Event Handler

```javascript
const Button = () => {
  const handleClick = () => {
    alert("Button clicked!");
  };

  return <button onClick={handleClick}>Click Me</button>;
};
```

### Example: Passing Callback as Prop

```javascript
const Child = ({ onAction }) => {
  return <button onClick={onAction}>Do Action</button>;
};

const Parent = () => {
  const handleAction = () => {
    alert("Action from child executed!");
  };

  return <Child onAction={handleAction} />;
};
```

**Explanation:**

- `Parent` passes `handleAction` as a **callback prop** to `Child`.
- When `Child` button is clicked, the callback runs.

---

## **When to Use Callbacks**

✔ Handling **async tasks** (like API calls).  
✔ Passing functions to **child components** in React.  
✔ Event handling for buttons, forms, etc.

---

### Summary

✔ Callbacks = Functions passed as arguments to other functions.  
✔ Used for **async operations** and **React props**.  
✔ Common in **event handling** and **communication between components**.

---
