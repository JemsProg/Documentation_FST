# React In-Depth: Render Props

**Render Props** is a React pattern for **sharing code between components** using a prop whose value is a function.

---

## **1. What is Render Props?**

- A **render prop** is a function prop that tells a component **what to render**.
- It allows **dynamic UI rendering** and **logic sharing** without inheritance or HOCs.

**Definition:**

```javascript
<Component render={(data) => <UI using={data} />} />
```

---

## **2. Why Use Render Props?**

✔ To share reusable **logic** between components.  
✔ To keep UI **flexible and dynamic**.  
✔ Alternative to **HOCs**.

---

## **3. Basic Example**

```javascript
const DataProvider = ({ render }) => {
  const data = "Hello from Render Props!";
  return render(data);
};

const App = () => {
  return <DataProvider render={(message) => <h1>{message}</h1>} />;
};

export default App;
```

**Output:**

```
Hello from Render Props!
```

**Explanation:**

- `DataProvider` passes `data` to `render` function prop.
- `App` decides **how to display it**.

---

## **4. Real Use Case: Mouse Tracker**

```javascript
import React, { useState } from "react";

const MouseTracker = ({ render }) => {
  const [position, setPosition] = useState({ x: 0, y: 0 });

  const handleMouseMove = (event) => {
    setPosition({ x: event.clientX, y: event.clientY });
  };

  return (
    <div onMouseMove={handleMouseMove} style={{ height: "100vh" }}>
      {render(position)}
    </div>
  );
};

const App = () => {
  return (
    <MouseTracker
      render={({ x, y }) => (
        <h1>
          Mouse Position: {x}, {y}
        </h1>
      )}
    />
  );
};

export default App;
```

**Explanation:**

- `MouseTracker` handles logic for mouse movement.
- `App` decides **what to render** using the position.

---

## **Render Props vs HOC**

| Feature          | Render Props                | HOC                            |
| ---------------- | --------------------------- | ------------------------------ |
| **How It Works** | Passes a function as a prop | Wraps component inside another |
| **Readability**  | More explicit               | Can be harder to follow        |
| **Preferred?**   | Use Hooks today             | Use Hooks today                |

---

## **Best Practices**

✔ Name the prop clearly (e.g., `render`, `children`).  
✔ Use with caution → Too many render props can cause **nested code**.  
✔ For modern React, prefer **Hooks** for logic sharing.

---

### Summary

✔ Render Props = Share logic using a **function prop**.  
✔ Flexible way to decide **what to render**.  
✔ Common alternative to HOCs before Hooks existed.

---
