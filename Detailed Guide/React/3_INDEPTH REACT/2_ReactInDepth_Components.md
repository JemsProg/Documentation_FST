
#  React In-Depth: Components

**Components** are the core building blocks of a React application.  
They allow developers to create **reusable, modular pieces of UI** that can be combined to form complex interfaces.

---

## **1. What is a Component?**
- A **component** is a function or class that returns **JSX** (UI elements).
- Components make your app **structured, reusable, and maintainable**.

Example of a simple component:
```javascript
const Greeting = () => {
  return <h1>Hello, React Components!</h1>;
};

export default Greeting;
```

---

## **2. Why Components?**
✔ **Reusability** – Write once, use anywhere.  
✔ **Organization** – Divide UI into smaller pieces.  
✔ **Maintainability** – Easier debugging and testing.

---

## **3. Types of Components**
React has two main types:

### ✅ **Functional Components** (Modern Approach)
- Simple JavaScript functions that return JSX.
- Can use **Hooks** (like `useState` and `useEffect`).
```javascript
const Header = () => <h1>Welcome to React!</h1>;
```

### ✅ **Class Components** (Older Approach)
- Use ES6 classes and `render()` method.
```javascript
import React, { Component } from "react";

class Header extends Component {
  render() {
    return <h1>Hello from Class Component!</h1>;
  }
}
```

**Note:** Functional components are preferred in modern React.

---

## **4. Component Naming Rules**
✔ Name must start with a **capital letter**.  
✔ Must **return JSX**.  
✔ Can accept **props** for customization.

Example:
```javascript
const Button = ({ label }) => <button>{label}</button>;
```

Usage:
```javascript
<Button label="Click Me" />
```

---

## **5. Combining Components (Composition)**
React apps are created by **nesting components**:
```javascript
const Header = () => <h1>Header</h1>;
const Footer = () => <p>Footer</p>;

const App = () => (
  <div>
    <Header />
    <p>Main Content</p>
    <Footer />
  </div>
);
```

---

### ✅ Summary
✔ Components = Reusable UI building blocks.  
✔ Types: **Functional (recommended)** & Class.  
✔ Components can accept **props** and can be combined for complex UIs.

---
