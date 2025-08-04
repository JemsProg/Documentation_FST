
#  React In-Depth: Conditional Rendering

**Conditional Rendering** in React means displaying different UI elements based on certain conditions, like user input, state values, or props.

---

## **1. What is Conditional Rendering?**
- It allows you to **show or hide components dynamically** based on conditions.
- Similar to using `if` statements in JavaScript, but applied in JSX.

---

## **2. Common Ways to Implement Conditional Rendering**

### ✅ **1. Using if Statements**
Example:
```javascript
const App = () => {
  const isLoggedIn = true;

  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  } else {
    return <h1>Please log in</h1>;
  }
};
```

---

###  **2. Using Ternary Operator**
Example:
```javascript
const App = () => {
  const isLoggedIn = false;

  return (
    <div>
      {isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please log in</h1>}
    </div>
  );
};
```

---

###  **3. Using Logical AND (`&&`)**
Best for rendering something **only if the condition is true**.
```javascript
const App = () => {
  const hasNotifications = true;

  return (
    <div>
      <h1>Dashboard</h1>
      {hasNotifications && <p>You have new notifications!</p>}
    </div>
  );
};
```

---

###  **4. Conditional Rendering with Functions**
Example:
```javascript
const getGreeting = (isLoggedIn) => {
  return isLoggedIn ? "Welcome back!" : "Please log in";
};

const App = () => {
  return <h1>{getGreeting(true)}</h1>;
};
```

---

## **When to Use Conditional Rendering**
✔ To handle **login/logout UI**.  
✔ To show **loading states** when fetching data.  
✔ To toggle **components or features** based on state or props.

Example (Loading State):
```javascript
const App = () => {
  const isLoading = true;

  return (
    <div>
      {isLoading ? <p>Loading...</p> : <p>Data Loaded!</p>}
    </div>
  );
};
```

---

###  Summary
✔ Conditional rendering = Show/hide UI based on conditions.  
✔ Use **if**, **ternary**, **&&**, or **functions** for clean code.  
✔ Common in **login systems**, **loading indicators**, **feature toggles**.

---
