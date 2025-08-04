# Modern JavaScript for React: Promises

A **Promise** in JavaScript represents the **eventual completion (or failure)** of an asynchronous operation and its resulting value.  
Promises are widely used for **API calls**, **asynchronous operations**, and **React data fetching**.

---

## **1. What is a Promise?**

- A Promise is an **object** that represents a value that will be available in the **future**.
- It can be in one of these states:
  - **Pending** → Initial state, not fulfilled or rejected.
  - **Fulfilled** → Operation completed successfully (resolved).
  - **Rejected** → Operation failed.

---

## **2. Creating a Promise**

```javascript
const myPromise = new Promise((resolve, reject) => {
  let success = true;

  if (success) {
    resolve("Promise resolved successfully!");
  } else {
    reject("Promise rejected!");
  }
});

myPromise
  .then((response) => console.log(response))
  .catch((error) => console.error(error));
```

**Output:**

```
Promise resolved successfully!
```

---

## **3. Using Promises with setTimeout (Example)**

```javascript
const wait = (ms) => {
  return new Promise((resolve) => setTimeout(resolve, ms));
};

wait(2000).then(() => console.log("Executed after 2 seconds"));
```

---

## **4. Chaining Promises**

You can chain `.then()` to handle multiple asynchronous steps.

```javascript
new Promise((resolve) => {
  resolve(2);
})
  .then((num) => {
    console.log(num); // 2
    return num * 2;
  })
  .then((num) => {
    console.log(num); // 4
  });
```

---

## **5. Promises in React**

Promises are used when fetching data from APIs.

Example using **fetch**:

```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```

---

## **When to Use Promises**

✔ API calls in React components.  
✔ Delaying actions or waiting for responses.  
✔ Handling multiple asynchronous tasks in sequence.

---

### Summary

✔ A Promise represents a value that will be available later.  
✔ Use `.then()` for success and `.catch()` for errors.  
✔ Common in **API calls** and **React data fetching**.

---
