# React In-Depth: Higher-Order Components (HOC)

A **Higher-Order Component (HOC)** is an **advanced React pattern** that allows you to **reuse component logic** by wrapping a component inside another component.

---

## **1. What is an HOC?**

- A Higher-Order Component is **a function that takes a component as input and returns a new component**.
- HOCs are used to **share logic** between components without repeating code.

**Definition:**

```javascript
const EnhancedComponent = higherOrderComponent(WrappedComponent);
```

---

## **2. Why Use HOCs?**

✔ To **reuse logic** across multiple components.  
✔ Commonly used for:

- Authentication checks.
- Permission-based UI.
- Logging or analytics.

---

## **3. Example: Basic HOC**

```javascript
import React from "react";

// HOC: Adds a message prop
const withMessage = (WrappedComponent) => {
  return (props) => {
    return <WrappedComponent {...props} message="Hello from HOC!" />;
  };
};

// Normal component
const Display = ({ message }) => <h1>{message}</h1>;

// Enhanced component using HOC
const EnhancedDisplay = withMessage(Display);

const App = () => <EnhancedDisplay />;

export default App;
```

**Output:**

```
Hello from HOC!
```

**Explanation:**

- `withMessage` is the HOC.
- It takes `Display` as input and returns `EnhancedDisplay`.

---

## **4. Passing Props Through HOC**

HOCs **must forward props** to keep components flexible.

Example:

```javascript
const withLogger = (WrappedComponent) => {
  return (props) => {
    console.log("Props:", props);
    return <WrappedComponent {...props} />;
  };
};
```

---

## **5. Real Use Case: Authentication Check**

```javascript
const withAuth = (WrappedComponent) => {
  return (props) => {
    const isLoggedIn = true; // Example
    return isLoggedIn ? (
      <WrappedComponent {...props} />
    ) : (
      <h1>Please Log In</h1>
    );
  };
};

const Dashboard = () => <h1>Welcome to Dashboard</h1>;

const ProtectedDashboard = withAuth(Dashboard);

const App = () => <ProtectedDashboard />;
```

---

## **HOC Best Practices**

✔ Do not modify the original component.  
✔ Always pass props using `{...props}`.  
✔ Use descriptive names for HOCs (e.g., `withAuth`, `withTheme`).

---

### Summary

✔ HOCs are **functions that return components**.  
✔ Useful for **code reuse** and **adding extra functionality**.  
✔ Modern React often prefers **Hooks** over HOCs for logic sharing.

---
