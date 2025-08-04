
#  React In-Depth: Hooks (useState & useEffect)

React **Hooks** allow you to use state and lifecycle features in **functional components**.  
The two most important hooks for beginners are **useState** and **useEffect**.

---

## **1. What is a Hook?**
- A Hook is a **special function** that lets you "hook into" React features like **state** and **lifecycle**.
- Hooks can only be used inside **functional components**.

---

## **2. The useState Hook**
`useState` allows you to add **state** to functional components.

###  Syntax:
```javascript
const [state, setState] = useState(initialValue);
```

###  Example: Counter with useState
```javascript
import React, { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};

export default Counter;
```

**Explanation:**
- `count` → current value of state.
- `setCount` → function to update state.
- React **re-renders** when `setCount` is called.

---

## **3. The useEffect Hook**
`useEffect` allows you to run **side effects** in functional components (e.g., fetching data, updating the DOM).

###  Syntax:
```javascript
useEffect(() => {
  // Code runs after component renders
}, [dependencies]);
```

---

###  Example: Logging on Render
```javascript
import React, { useState, useEffect } from "react";

const App = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log("Component rendered or count changed");
  }, [count]);

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};

export default App;
```

**Explanation:**
- `useEffect` runs after every render **when dependencies change**.
- `[count]` → dependency array, effect runs when `count` changes.

---

###  Example: Fetching Data with useEffect
```javascript
import React, { useEffect, useState } from "react";

const App = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/posts/1")
      .then(response => response.json())
      .then(data => setData(data));
  }, []); // Empty array = runs only once (on mount)

  return <div>{data ? data.title : "Loading..."}</div>;
};

export default App;
```

---

##  **Rules of Hooks**
✔ Only call Hooks **at the top level** of your component.  
✔ Only call Hooks **from React functions** (not inside loops, conditions, or nested functions).  

---

###  Summary
✔ `useState` → Manages **state** in functional components.  
✔ `useEffect` → Handles **side effects** (API calls, DOM updates).  
✔ Hooks make functional components **powerful and stateful**.

---
