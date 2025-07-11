# 🔄 React `useEffect` Hook: What & How (Beginner-Friendly Guide)

This documentation explains **what `useEffect` is in React, how it works**, and provides an easy-to-follow example for beginners.

---

## ❓ What is `useEffect`?

✅ `useEffect` is a **React Hook** that lets you perform **side effects** in your functional components.  
Side effects are things that happen *outside* of rendering your component, such as:
- Fetching data from an API
- Updating the page title
- Adding or removing event listeners

Before Hooks, side effects could only be done in class components using lifecycle methods like `componentDidMount` and `componentDidUpdate`.  
Now, functional components can do this too — thanks to `useEffect`!

---

## 🔷 How Does `useEffect` Work?

✅ You import it from React:
```jsx
import { useEffect } from "react";
```

✅ Then you use it inside your component:
```jsx
useEffect(() => {
  // your side effect code here
}, [dependencies]);
```

- The function inside `useEffect()` runs **after the component renders**.
- The `dependencies` array determines when the effect runs:
  - `[]` → runs only once (on mount).
  - `[someValue]` → runs whenever `someValue` changes.
  - No array → runs on *every* render.

---

## 🧩 Example: Fetching Data

Here’s a beginner-friendly example where we fetch data from an API when the component loads:

```jsx
import { useState, useEffect } from "react";
import axios from "axios";

function UserList() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    const fetchUsers = async () => {
      const res = await axios.get("https://jsonplaceholder.typicode.com/users");
      setUsers(res.data);
    };

    fetchUsers();
  }, []); // runs once when the component mounts

  return (
    <div>
      <h2>User List</h2>
      <ul>
        {users.map((user) => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default UserList;
```

✅ What happens here:
- `useEffect` runs `fetchUsers()` only once when the page loads.
- `fetchUsers()` gets the user data and updates `users` state.
- The component re-renders with the updated `users` list.

---

## 📝 Tips: Do’s and Don’ts

✅ **Do:**
- Always include a dependency array (`[]`) when you only want to run it once.
- Use async/await functions *inside* `useEffect`.

🚫 **Don’t:**
- Don’t call `useEffect` conditionally — Hooks must always be called in the same order.
- Don’t forget dependencies — always include variables used in the effect in the dependencies array.

---

## 🏁 Summary: What & How

✅ **What is it?**
- A React Hook to perform side effects in functional components.

✅ **How does it work?**
- Runs code after rendering.
- Controlled by the `dependencies` array to determine when it runs.

🎉 That’s it — now you know what `useEffect` is, how it works, and how to use it properly!

---

🔗 Learn more: [React Docs: useEffect](https://react.dev/reference/react/useEffect)
