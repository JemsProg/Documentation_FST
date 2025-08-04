# React In-Depth: Event Handling

React uses a special way to handle events in components.  
Event handling in React is similar to HTML but with **some important differences**.

---

## **1. What is Event Handling in React?**

Event handling means responding to **user actions** like clicks, form submissions, typing in inputs, etc.

---

## **2. Differences Between HTML and React Events**

✔ React uses **camelCase** for event names (e.g., `onClick`, not `onclick`).  
✔ Event handlers are passed as **functions**, not strings.

**HTML Example:**

```html
<button onclick="alert('Clicked!')">Click Me</button>
```

**React Example:**

```javascript
<button onClick={() => alert("Clicked!")}>Click Me</button>
```

---

## **3. Adding Event Handlers in React**

You can attach an event handler to an element using JSX.

Example:

```javascript
const App = () => {
  const handleClick = () => {
    alert("Button was clicked!");
  };

  return <button onClick={handleClick}>Click Me</button>;
};

export default App;
```

---

## **4. Passing Arguments to Event Handlers**

You can pass arguments by using an **arrow function**.

Example:

```javascript
const App = () => {
  const greet = (name) => {
    alert(`Hello, ${name}!`);
  };

  return <button onClick={() => greet("Alice")}>Greet</button>;
};
```

---

## **5. Handling Events in Forms**

React uses **controlled components** to handle form input values.

Example:

```javascript
import React, { useState } from "react";

const App = () => {
  const [input, setInput] = useState("");

  const handleChange = (event) => {
    setInput(event.target.value);
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    alert(`You typed: ${input}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input type="text" value={input} onChange={handleChange} />
      <button type="submit">Submit</button>
    </form>
  );
};

export default App;
```

**Explanation:**

- `onChange` updates state as the user types.
- `onSubmit` prevents page reload and shows the typed input.

---

## **Event Object**

React provides an **event object** similar to native events but with **synthetic events**.

Example:

```javascript
const handleClick = (event) => {
  console.log(event.target); // The button element
};
```

---

### Summary

✔ Event names use **camelCase** (`onClick`, `onChange`).  
✔ Handlers are functions, not strings.  
✔ Use **controlled components** for forms.  
✔ Use `event.preventDefault()` to stop default behavior.

---
