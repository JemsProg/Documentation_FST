# React In-Depth: Lifecycle Events

**Lifecycle events** refer to the different phases a React component goes through during its existence:

- **Mounting** (component is added to the DOM)
- **Updating** (component re-renders due to state/props changes)
- **Unmounting** (component is removed from the DOM)

React provides ways to run code during these phases.

---

## **1. Lifecycle in Class Components**

Class components have specific lifecycle methods:

| Phase      | Method                   |
| ---------- | ------------------------ |
| Mounting   | `componentDidMount()`    |
| Updating   | `componentDidUpdate()`   |
| Unmounting | `componentWillUnmount()` |

### Example:

```javascript
import React, { Component } from "react";

class App extends Component {
  componentDidMount() {
    console.log("Component Mounted");
  }

  componentDidUpdate() {
    console.log("Component Updated");
  }

  componentWillUnmount() {
    console.log("Component Unmounted");
  }

  render() {
    return <h1>Hello Lifecycle</h1>;
  }
}
```

---

## **2. Lifecycle in Functional Components (useEffect)**

Functional components use **`useEffect`** to handle lifecycle events.

### ✅ Example:

```javascript
import React, { useState, useEffect } from "react";

const App = () => {
  const [count, setCount] = useState(0);

  // Runs after every render
  useEffect(() => {
    console.log("Component Rendered or Updated");
  });

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
};
```

---

## **3. Controlling useEffect with Dependencies**

- **No dependencies** → Runs after every render.
- **Empty array `[]`** → Runs only once (on mount).
- **With values `[count]`** → Runs when those values change.

### Example:

```javascript
useEffect(() => {
  console.log("Runs only when count changes");
}, [count]);
```

---

## **4. Cleanup Function (Unmount)**

You can return a function inside `useEffect` to clean up resources.

### Example:

```javascript
useEffect(() => {
  const timer = setInterval(() => {
    console.log("Running...");
  }, 1000);

  return () => clearInterval(timer); // Cleanup on unmount
}, []);
```

---

## **Common Uses of Lifecycle Events**

✔ Fetching data on mount.  
✔ Subscribing/unsubscribing to events.  
✔ Cleaning up timers or listeners.

---

### Summary

✔ Class components use **lifecycle methods**.  
✔ Functional components use **`useEffect`** for all lifecycle phases.  
✔ Always use **cleanup** for performance and memory safety.

---
