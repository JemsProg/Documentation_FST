
#  React In-Depth: State

**State** is a built-in feature in React used to store and manage data that changes over time.  
When state changes, React **re-renders the component** to update the UI.

---

## **1. What is State?**
- State is **data managed by a component**.
- Unlike props, **state is local** to a component and can change during the component's lifecycle.

Example:
```javascript
const [count, setCount] = useState(0);
```

**Explanation:**
- `count` → current state value.
- `setCount` → function to update the state.

---

## **2. Why Use State?**
✔ To make your UI **dynamic and interactive**.  
✔ For data that **changes over time** (e.g., form input, counters, API data).  

---

## **3. Using State with useState Hook**
The `useState` hook is used in **functional components** to create state.

###  Example: Counter App
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
- `useState(0)` → initializes state with 0.
- `setCount(count + 1)` → updates state.
- React **re-renders the component** when state changes.

---

## **4. State vs Props**
| Feature | State | Props |
|---------|-------|-------|
| **Definition** | Internal data of a component | Data passed from parent |
| **Mutable?** | ✅ Yes (can change) | ❌ No (read-only) |
| **Who updates it?** | The component itself | Parent component |

---

##  **Best Practices for State**
✔ Do **not modify state directly** (use `setState` or `setCount`).  
✔ Keep state minimal (only what changes).  
✔ Use **separate states** for unrelated data.

Bad Example ❌:
```javascript
count = 5; // Direct mutation
```

Good Example ✅:
```javascript
setCount(5);
```

---

###  Summary
✔ State = **Local data** that changes over time.  
✔ Use `useState` hook in functional components.  
✔ React re-renders UI when state updates.

---
