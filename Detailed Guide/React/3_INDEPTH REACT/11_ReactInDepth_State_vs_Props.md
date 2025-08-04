
#  React In-Depth: State vs Props

In React, **State** and **Props** are two fundamental concepts used to manage and pass data in a component-based architecture.  
Understanding the difference between them is essential for building dynamic applications.

---

## **1. What is State?**
- State is **internal data** that belongs to a component.
- State can **change over time** (mutable).
- When state changes, **React re-renders the component**.

Example:
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

---

## **2. What are Props?**
- Props (short for **properties**) are **read-only data passed from parent to child components**.
- Props cannot be changed by the child component.

Example:
```javascript
const Greeting = ({ name }) => <h1>Hello, {name}!</h1>;

const App = () => <Greeting name="Alice" />;
```

**Output:**
```
Hello, Alice!
```

---

## **3. Key Differences Between State and Props**
| Feature       | State                         | Props                               |
|--------------|------------------------------|-------------------------------------|
| **Definition** | Internal data of a component | Data passed from parent to child    |
| **Mutable?** | ✅ Yes (can change)           | ❌ No (read-only)                   |
| **Who sets it?** | Component itself            | Parent component                   |
| **Purpose**   | Handle dynamic data          | Pass data for customization         |

---

## **4. When to Use State vs Props**
✔ Use **State** when the component needs to **manage its own data** (like form inputs, counters).  
✔ Use **Props** to **send data from parent to child** (like user info, settings).  

---

##  **Example: State + Props Together**
```javascript
const Display = ({ value }) => <h2>Current Value: {value}</h2>;

const App = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <Display value={count} />
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
};
```

**Explanation:**
- `App` manages state (`count`).
- `Display` gets `count` as a **prop**.

---

###  Summary
✔ **State** → Component’s own data, can change over time.  
✔ **Props** → Data passed from parent, read-only.  
✔ Both work together to build **dynamic and reusable components**.

---
