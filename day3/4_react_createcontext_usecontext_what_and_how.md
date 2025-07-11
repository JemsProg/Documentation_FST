# 🌐 React `createContext` and `useContext`: What & How (Beginner-Friendly Guide)

This documentation explains **what `createContext` and `useContext` are in React, how to use them**, and provides a clear, realistic example for authentication in an e-commerce system.

---

## ❓ What is `createContext` and `useContext`?

✅ `createContext` is a React API that creates a **Context object** for sharing data globally across components without prop drilling.  

✅ `useContext` is a React Hook that lets you access the value of a Context from any child component.

Why use them?
- To share state (like authentication, theme, or language) across components, even deeply nested ones, without passing props through every level.

---

## 🔷 How to Use Them?

✅ You typically use them together in 3 steps:

1️⃣ Create the Context:  
```jsx
export const AuthContext = createContext();
```

2️⃣ Provide the Context (at a high level, e.g., App.jsx):  
```jsx
<AuthContext.Provider value={{ key: value }}>
  {children}
</AuthContext.Provider>
```

3️⃣ Consume the Context in a child component:  
```jsx
const contextValue = useContext(AuthContext);
```

---

## 🛒 E-Commerce Example: Authentication Context

Here’s how you can manage **authentication state globally** using `createContext` and `useContext`.

---

### 📄 `src/context/AuthProvider.jsx`

This file creates the context and provides it to all components.

```jsx
import React, { createContext, useState, useEffect } from "react";
import { useLocation } from "react-router-dom";

export const AuthContext = createContext();

export const AuthProvider = ({ children }) => {
  const [isAuthenticated, setIsAuthenticated] = useState(false);
  const location = useLocation();

  useEffect(() => {
    const token = localStorage.getItem("access_token");
    if (token) {
      setIsAuthenticated(true);
    } else {
      setIsAuthenticated(false);
    }
  }, [location]);

  return (
    <AuthContext.Provider value={{ isAuthenticated, setIsAuthenticated }}>
      {children}
    </AuthContext.Provider>
  );
};
```

✅ What happens here:
- We check for an `access_token` in localStorage whenever the route (`location`) changes.
- If the token exists, we set `isAuthenticated` to `true`.
- We wrap our app in `AuthProvider`, passing `isAuthenticated` and `setIsAuthenticated` to all children.

---

### 📄 `src/components/PrivateRoute.jsx`

This file consumes the context to protect certain routes.

```jsx
import React, { useContext } from "react";
import { Navigate } from "react-router-dom";
import { AuthContext } from "../../context/AuthProvider";

const PrivateRoute = ({ children }) => {
  const { isAuthenticated } = useContext(AuthContext);

  return isAuthenticated ? children : <Navigate to="/login" />;
};

export default PrivateRoute;
```

✅ What happens here:
- We use `useContext` to get `isAuthenticated` from `AuthContext`.
- If authenticated → show the requested page.
- If not → redirect to `/login`.

---

### 📄 `App.jsx`

We wrap our entire app in `<AuthProvider>` to provide the context to all routes.

```jsx
<AuthProvider>
  <Routes>
    <Route path="/profile" element={
      <PrivateRoute><Profile /></PrivateRoute>
    } />
  </Routes>
</AuthProvider>
```

✅ Now any component inside `AuthProvider` can access `isAuthenticated` using `useContext(AuthContext)`.

---

## 📝 Tips: Do’s and Don’ts

✅ **Do:**
- Use `createContext` for global state that many components need.
- Always wrap your app with the `Provider` at a high level.
- Keep your context values simple.

🚫 **Don’t:**
- Overuse context for deeply nested but unrelated state.
- Mutate context values directly — always use the setter function.

---

## 🏁 Summary: What & How

✅ **What is it?**
- `createContext`: lets you create global state that can be shared across components.
- `useContext`: lets you read that global state from any component.

✅ **How to use?**
1. Create the context.
2. Wrap your app in the `Provider`.
3. Use `useContext` to access the data.

🎉 That’s it — you now know how to use `createContext` and `useContext` for global state management in your React e-commerce app!

---

🔗 Learn more: [React Docs: Context](https://react.dev/reference/react/createContext)
