# React Beginner Guide

## Table of Contents

1. [An Introduction to React](#an-introduction-to-react)
2. [How to Use create-react-app](#how-to-use-create-react-app)

---

## **An Introduction to React**

React is a **JavaScript library for building user interfaces**. It allows developers to create **dynamic and interactive web applications** using a component-based architecture.

### **What is React?**

- A library created by **Facebook**.
- Used to build **single-page applications (SPAs)**.
- Uses a **component-based structure** to break down UIs into reusable pieces.

### **Why Use React?**

- **Reusable Components** → Build once, use multiple times.
- **Virtual DOM** → Faster updates and rendering.
- **Rich Ecosystem** → Works well with tools like Tailwind, Redux, and APIs.

### **When to Use React?**

- When building **interactive web apps** (e.g., dashboards, e-commerce).
- When you want **fast UI updates** without refreshing the page.

### **How React Works**

- Components → Small building blocks (Header, Button, Card).
- JSX → Allows writing HTML inside JavaScript.
- State & Props → Manage and pass data between components.

**Example of a Simple React Component:**

```javascript
function Welcome() {
  return <h1>Hello, React!</h1>;
}
export default Welcome;
```

---

## **How to Use create-react-app**

`create-react-app` is an official tool to **set up a React project quickly** without configuring Webpack or Babel manually.

### **Step 1: Install Node.js**

- Download and install Node.js from: [https://nodejs.org](https://nodejs.org)
- Check version:

```bash
node -v
npm -v
```

### **Step 2: Create a New React App**

Run this command in your terminal:

```bash
npx create-react-app my-app
```

- `npx` ensures you are using the latest version of the tool.
- `my-app` is the project folder name.

### **Step 3: Navigate and Start the App**

```bash
cd my-app
npm start
```

- Opens the app in your browser at `http://localhost:3000`.

### **Project Structure Overview**

```
my-app/
├── node_modules/     # Installed dependencies
├── public/           # Static assets
├── src/              # React components & logic
│   ├── App.js        # Main App component
│   └── index.js      # Entry point
└── package.json      # Project info & scripts
```

**Default Output:** A spinning React logo with a basic layout.

---
