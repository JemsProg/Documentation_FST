# 🚦 React Routes Guide

React Router is the standard routing library for React. It enables navigation among views of various components, handling browser history and dynamic URL paths.

---

## ✅ What You'll Learn

- How to install and set up React Router
- Explanation of `BrowserRouter`, `Routes`, `Route`, `Link`, and `useParams`
- Defining routes for different pages
- Navigating between pages using `Link`
- Route parameters and nested routes

---

## 📦 Installation

Install `react-router-dom` in your React project:

```bash
npm install react-router-dom
```

---

## 📁 Folder Structure Example

```
src/
├── App.jsx
├── pages/
│   ├── Home.jsx
│   ├── About.jsx
│   └── Product.jsx
```

---

## 🛠️ Basic Setup in App.jsx

```jsx
import {
  BrowserRouter as Router,
  Routes,
  Route
} from 'react-router-dom';

import Home from './pages/Home';
import About from './pages/About';
import Product from './pages/Product';

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/product/:id" element={<Product />} />
      </Routes>
    </Router>
  );
}

export default App;
```

---

## 🧩 Explanation of Key Concepts

### `BrowserRouter`
Wraps the entire application to enable routing functionality using the browser's history API. Often renamed as `Router` for simplicity.

### `Routes`
A container that holds all your `Route` components. Replaces the older `Switch` from React Router v5.

### `Route`
Defines a path and the corresponding component to render. Supports dynamic segments like `:id`.

### `Link`
Used for navigation. Unlike `<a>`, it doesn’t reload the page and works seamlessly with React Router.

```jsx
<Link to="/about">About</Link>
```

### `useParams`
A hook to access route parameters (e.g., `:id`). Commonly used in dynamic routes like `/product/:id`.

---

## 🔗 Navigation with `Link`

```jsx
import { Link } from 'react-router-dom';

function Navbar() {
  return (
    <nav>
      <Link to="/">Home</Link>
      <Link to="/about">About</Link>
    </nav>
  );
}
```

---

## 🧭 Accessing Route Parameters

For a route like `/product/:id`, access the `id` with:

```jsx
import { useParams } from 'react-router-dom';

function Product() {
  const { id } = useParams();
  return <h1>Viewing Product #{id}</h1>;
}
```

---

## 🧠 Tips for Beginners

- Always wrap your routes inside `<BrowserRouter>` (alias `Router`).
- Use `Link` instead of `<a>` to avoid full page reloads.
- `Routes` replaces the older `Switch` in React Router v6.
- Route paths are matched from top to bottom. Be specific!

---

You're now ready to handle navigation in your React apps! 🚀

