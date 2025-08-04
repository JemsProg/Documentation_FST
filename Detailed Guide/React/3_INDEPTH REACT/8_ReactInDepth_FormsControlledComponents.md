
#  React In-Depth: Forms and Controlled Components

Handling forms in React is different from plain HTML.  
React uses **controlled components** to manage form inputs using state.

---

## **1. What is a Controlled Component?**
- In React, a **controlled component** is an input element whose **value is controlled by React state**.
- The input field's value is set via `value` attribute and updated using `onChange`.

---

## **2. Example: Basic Controlled Input**
```javascript
import React, { useState } from "react";

const App = () => {
  const [name, setName] = useState("");

  const handleChange = (event) => {
    setName(event.target.value);
  };

  return (
    <div>
      <input type="text" value={name} onChange={handleChange} />
      <p>Hello, {name}</p>
    </div>
  );
};

export default App;
```

**Explanation:**
- `value={name}` → input value comes from state.
- `onChange` → updates state when user types.

---

## **3. Handling Multiple Inputs**
You can use one handler for multiple inputs:
```javascript
import React, { useState } from "react";

const App = () => {
  const [form, setForm] = useState({ email: "", password: "" });

  const handleChange = (e) => {
    setForm({ ...form, [e.target.name]: e.target.value });
  };

  return (
    <form>
      <input
        name="email"
        type="email"
        value={form.email}
        onChange={handleChange}
      />
      <input
        name="password"
        type="password"
        value={form.password}
        onChange={handleChange}
      />
      <p>Email: {form.email}</p>
    </form>
  );
};

export default App;
```

---

## **4. Handling Form Submission**
Use `onSubmit` and `event.preventDefault()` to prevent page reload.

Example:
```javascript
const handleSubmit = (event) => {
  event.preventDefault();
  alert(`Submitted: ${name}`);
};

<form onSubmit={handleSubmit}>
  <input type="text" value={name} onChange={handleChange} />
  <button type="submit">Submit</button>
</form>
```

---

## ✅ **Controlled vs Uncontrolled Components**
| Feature | Controlled | Uncontrolled |
|---------|-----------|-------------|
| **Value** | Managed by React state | Managed by the DOM |
| **onChange** | Required | Optional |
| **Preferred?** | ✅ Yes | Rarely |

---

### ✅ Summary
✔ Controlled components = Inputs controlled by React state.  
✔ Use `onChange` to update state.  
✔ Use `onSubmit` to handle form submission without reload.

---
