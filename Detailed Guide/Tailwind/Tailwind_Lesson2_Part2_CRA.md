# Tailwind CSS v4.1 - Lesson 2 (Part 2): Installing Tailwind in React using Create React App (CRA)

If you prefer **Create React App (CRA)** for your projects, Tailwind CSS works perfectly with it too.  
Follow these steps to set it up:

---

## **1. Create a React Project using CRA**

Run the following command:

```bash
npx create-react-app my-app
cd my-app
```

---

## **2. Install Tailwind CSS and Dependencies**

Install Tailwind and its PostCSS plugins:

```bash
npm install tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

This creates:

```
tailwind.config.js
postcss.config.js
```

`tailwind.config.js` is optional in Tailwind v4.1 but useful for customization.

---

## **3. Configure Tailwind in index.css**

Open `src/index.css` and **replace its content** with:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

✔ These directives bring in Tailwind's **base styles**, **components**, and **utilities**.

---

## **4. Check Tailwind Content Paths (Optional Customization)**

By default, Tailwind v4.1 uses modern scanning, but if you customize, ensure `tailwind.config.js` includes:

```javascript
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

---

## **5. Import index.css in index.js**

Ensure your `src/index.js` has:

```javascript
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css"; // ✅ Import Tailwind CSS
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

---

CRA is now set up with Tailwind!  
**Next:** We’ll add Tailwind directives (done) and **test Tailwind by applying `bg-red-500` to a div** in Part 3.

---
