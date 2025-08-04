
#  React In-Depth: The Context API

The **Context API** in React provides a way to **share data across multiple components** without passing props manually at every level.  
It solves the problem of **prop drilling**.

---

## **1. What is Prop Drilling?**
Prop drilling happens when you pass data through multiple components that don’t need it, just to reach a deeply nested child.

Example:
```javascript
const App = () => <Parent />;

const Parent = () => <Child name="Alice" />;

const Child = ({ name }) => <h1>{name}</h1>;
```

For large apps, this becomes **hard to manage**.

---

## **2. Why Use Context API?**
✔ Avoid **prop drilling**.  
✔ Share **global data** like theme, authentication status, language.  

---

## **3. How Context API Works**
Steps:
1. **Create a Context**.
2. **Provide the Context** at a high level in the component tree.
3. **Consume the Context** in any child component.

---

## **4. Example: Using Context API**
```javascript
import React, { createContext, useState, useContext } from "react";

// Step 1: Create Context
const ThemeContext = createContext();

// Step 2: Create Provider Component
const ThemeProvider = ({ children }) => {
  const [theme, setTheme] = useState("light");
  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};

// Step 3: Consume Context
const ThemedComponent = () => {
  const { theme, setTheme } = useContext(ThemeContext);
  return (
    <div style={{ background: theme === "light" ? "#fff" : "#333", color: theme === "light" ? "#000" : "#fff" }}>
      <p>Current theme: {theme}</p>
      <button onClick={() => setTheme(theme === "light" ? "dark" : "light")}>Toggle Theme</button>
    </div>
  );
};

const App = () => {
  return (
    <ThemeProvider>
      <ThemedComponent />
    </ThemeProvider>
  );
};

export default App;
```

---

##  **When to Use Context**
✔ Theme toggling (light/dark).  
✔ Authentication state (user login info).  
✔ Language/Localization settings.  

---

##  **Best Practices**
✔ Use Context for **global state** only.  
✔ Avoid overusing Context for everything (it can cause unnecessary re-renders).  
✔ For large apps, consider **Redux or Zustand** for state management.

---

###  Summary
✔ Context API solves **prop drilling**.  
✔ Use `createContext`, `Provider`, and `useContext`.  
✔ Best for **global state** like theme and auth.

---
