# Tailwind CSS v4.1 - Lesson 2 (Part 1): Installing Tailwind in React using Vite

In this lesson, we’ll set up Tailwind CSS in a **React project using Vite**. Vite is a modern build tool that is **faster and lighter** than Create React App.

---

## **1. Why Use Vite for React + Tailwind?**

✔ Super fast development with **hot module replacement**.  
✔ Minimal configuration.  
✔ Works perfectly with **Tailwind CSS v4.1**.

---

## **2. Step 1: Create a React Project with Vite**

Run these commands in your terminal:

```bash
# Create a Vite project
npm create vite@latest my-app

# Navigate to the folder
cd my-app

# Install dependencies
npm install
```

When prompted:

```
✔ Select a framework: React
✔ Select a variant: JavaScript or TypeScript (choose one)
```

---

## **3. Step 2: Install Tailwind CSS and Dependencies**

Run this command:

```bash
npm install tailwindcss postcss autoprefixer
```

Then initialize Tailwind (optional config file):

```bash
npx tailwindcss init -p
```

This creates:

```
tailwind.config.js
postcss.config.js
```

> In Tailwind v4.1, `tailwind.config.js` is optional, but it’s useful if you want customization later.

---

## **4. Step 3: Add Tailwind Directives in index.css**

In `src/index.css`, replace content with:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

This ensures Tailwind’s styles are applied globally.

---

## **5. Step 4: Import index.css in main.jsx**

Make sure your `main.jsx` has:

```javascript
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";
import "./index.css"; // ✅ Import Tailwind CSS here

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

---

Now Tailwind is installed in your Vite + React project!  
**Next:** We’ll add directives and **test Tailwind by applying `bg-red-500` to a div**.

---
