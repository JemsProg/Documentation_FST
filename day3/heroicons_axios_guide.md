# 📄 Guide: Installing and Using @heroicons/react and Axios

---

## 🖼️ @heroicons/react

### ✅ What is it?

[@heroicons/react](https://heroicons.com/) is a library of free, MIT-licensed high-quality SVG icons, designed for TailwindCSS but usable in any React project.

It gives you access to two sets of icons:

- **Outline** (stroke-style)
- **Solid** (filled-style)

These icons are shipped as React components for easy use.

---

### 📝 How to install

Run:

```bash
npm install @heroicons/react
```

---

### 🖋️ How to use

Import the icon component you need, then render it like any other React component:

```jsx
import { ShoppingCartIcon } from "@heroicons/react/24/outline";

function MyComponent() {
  return <ShoppingCartIcon className="h-6 w-6 text-gray-500" />;
}
```

You can customize the size and color with CSS classes.

---

### 📄 Learn more

Official website & documentation: 🔗 [https://heroicons.com/](https://heroicons.com/)

---

## 🌐 Axios

### ✅ What is it?

[Axios](https://axios-http.com/) is a promise-based HTTP client for JavaScript. It works in browsers and Node.js, and it’s often used in React apps to make HTTP requests to APIs.

It makes it easy to:

- Send GET, POST, PUT, DELETE requests.
- Handle JSON data.
- Automatically transform response/request data.
- Add headers, authentication tokens, and more.

---

### 📝 How to install

Run:

```bash
npm install axios
```

---

### 🖋️ How to use

Basic GET example:

```jsx
import axios from "axios";

axios.get("https://api.example.com/data")
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });
```

Basic POST example:

```jsx
axios.post("https://api.example.com/data", { key: "value" })
  .then(response => console.log(response))
  .catch(error => console.error(error));
```

In React, you usually use it inside `useEffect` or event handlers.

---

### 📄 Learn more

Official documentation: 🔗 [https://axios-http.com/](https://axios-http.com/)

---

✅ Both `@heroicons/react` and `axios` are widely-used tools that make building modern React applications easier and more efficient.

