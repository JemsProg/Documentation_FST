# React Concept: Composition

**Composition** in React is the practice of **building complex UIs by combining smaller, reusable components**.  
Instead of creating one large component, you break it into smaller pieces and **compose them together**.

---

## **1. What is Composition?**

- It’s like building with LEGO blocks: **combine smaller pieces into a bigger structure**.
- React encourages **component-based architecture** for better organization and reuse.

---

## **2. Why Composition?**

✔ Reusability – Write once, use multiple times.  
✔ Maintainability – Smaller components are easier to debug and test.  
✔ Scalability – Easier to manage large projects.

---

## **3. Basic Example of Composition**

```javascript
const Header = () => (
  <header>
    <h1>My Website</h1>
  </header>
);
const Footer = () => (
  <footer>
    <p>&copy; 2025</p>
  </footer>
);
const Main = () => (
  <main>
    <p>Welcome to my website!</p>
  </main>
);

const App = () => {
  return (
    <div>
      <Header />
      <Main />
      <Footer />
    </div>
  );
};

export default App;
```

**Explanation:**

- `App` component **composes** `Header`, `Main`, and `Footer` components to form the UI.

---

## **4. Composition with Children**

React provides `props.children` to allow **nesting components dynamically**.

### Example:

```javascript
const Card = ({ children }) => {
  return <div className="card">{children}</div>;
};

const App = () => {
  return (
    <Card>
      <h2>Product Title</h2>
      <p>Price: $10</p>
    </Card>
  );
};
```

**Output:**

```
<div class="card">
  <h2>Product Title</h2>
  <p>Price: $10</p>
</div>
```

---

## **Composition in Real Projects**

- Building **layouts** with Navbar, Sidebar, and Main Content.
- Creating **reusable UI elements** like Buttons, Cards, Modals.

Example:

```javascript
const Button = ({ label }) => <button>{label}</button>;

const App = () => (
  <div>
    <Button label="Login" />
    <Button label="Sign Up" />
  </div>
);
```

---

### Summary

✔ Composition = Combine small components to build larger UIs.  
✔ Use `props.children` for flexible layouts.  
✔ Encourages **clean, reusable, and maintainable code**.

---
