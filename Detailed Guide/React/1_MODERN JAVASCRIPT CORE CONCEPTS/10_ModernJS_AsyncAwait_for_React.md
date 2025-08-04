# Modern JavaScript for React: Async/Await

**Async/Await** is a modern way to handle asynchronous code in JavaScript.  
It makes asynchronous code look and behave more like synchronous code, making it easier to read and maintain.

---

## **1. What is Async/Await?**

- Introduced in **ES8**.
- **async** keyword → Makes a function return a Promise.
- **await** keyword → Pauses execution until the Promise resolves.

---

## **2. Basic Syntax**

```javascript
async function fetchData() {
  const response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
  const data = await response.json();
  console.log(data);
}

fetchData();
```

**Explanation:**

- `async` makes `fetchData()` return a Promise.
- `await` waits for `fetch()` and `response.json()` to complete before continuing.

---

## **3. Handling Errors with try...catch**

```javascript
async function getData() {
  try {
    const response = await fetch(
      "https://jsonplaceholder.typicode.com/posts/1"
    );
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}

getData();
```

---

## **4. Combining with Promises**

You can mix `async/await` with `Promise.all()` to handle multiple asynchronous tasks.

```javascript
async function fetchMultiple() {
  const [post, user] = await Promise.all([
    fetch("https://jsonplaceholder.typicode.com/posts/1").then((res) =>
      res.json()
    ),
    fetch("https://jsonplaceholder.typicode.com/users/1").then((res) =>
      res.json()
    ),
  ]);

  console.log("Post:", post);
  console.log("User:", user);
}

fetchMultiple();
```

---

## **Why Async/Await?**

✔ Easier to read than `.then()` chaining.  
✔ Makes asynchronous code look synchronous.  
✔ Perfect for **React API calls** in `useEffect`.

---

## **Async/Await in React**

Example: Fetching data inside a component:

```javascript
import React, { useEffect, useState } from "react";

const App = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      const response = await fetch(
        "https://jsonplaceholder.typicode.com/posts/1"
      );
      const result = await response.json();
      setData(result);
    };

    fetchData();
  }, []);

  return <div>{data ? data.title : "Loading..."}</div>;
};

export default App;
```

---

### Summary

✔ `async` makes a function return a Promise.  
✔ `await` pauses execution until the Promise resolves.  
✔ Use **try...catch** for error handling.  
✔ Common in **React for fetching data in hooks**.

---
