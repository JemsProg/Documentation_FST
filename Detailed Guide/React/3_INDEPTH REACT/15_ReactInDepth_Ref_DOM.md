# React In-Depth: Referencing a DOM Element

Sometimes in React, you need direct access to a **DOM element** (e.g., focusing an input, controlling animations).  
React provides the **`useRef` hook** for this purpose.

---

## **1. Why Use a Ref?**

✔ To **access a DOM element directly**.  
✔ To **store values that persist between renders** (without causing re-renders).

**Common use cases:**

- Focusing an input field.
- Playing or pausing a video.
- Storing previous state values.

---

## **2. Using `useRef` to Access DOM**

### Example: Focus an Input on Button Click

```javascript
import React, { useRef } from "react";

const App = () => {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus(); // Access the input DOM element
  };

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="Type here..." />
      <button onClick={focusInput}>Focus Input</button>
    </div>
  );
};

export default App;
```

**Explanation:**

- `useRef(null)` creates a ref object.
- `ref={inputRef}` attaches the ref to the input.
- `inputRef.current` gives direct access to the input element.

---

## **3. useRef vs State**

- **State** → Causes a re-render when updated.
- **useRef** → Does **NOT** cause re-render, making it perfect for DOM manipulation or storing values.

---

## **4. useRef for Storing Previous Values**

You can use `useRef` to store a value across renders without triggering a re-render.

Example:

```javascript
import React, { useState, useRef, useEffect } from "react";

const App = () => {
  const [count, setCount] = useState(0);
  const prevCount = useRef(0);

  useEffect(() => {
    prevCount.current = count;
  }, [count]);

  return (
    <div>
      <p>Current: {count}</p>
      <p>Previous: {prevCount.current}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
};

export default App;
```

---

## **Best Practices**

✔ Do not use refs for **state management** (use `useState` instead).  
✔ Use refs for **imperative actions** (focus, scroll, animations).

---

### Summary

✔ Use `useRef` to **reference DOM elements** without causing re-renders.  
✔ Perfect for input focus, media controls, and persisting values between renders.  
✔ Avoid using refs for UI state logic.

---
