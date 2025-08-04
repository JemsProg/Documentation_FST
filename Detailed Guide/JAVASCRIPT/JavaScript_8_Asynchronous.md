
#  Asynchronous JavaScript (ES6)

JavaScript is single-threaded, meaning it executes one task at a time. Asynchronous programming allows you to perform tasks like fetching data **without blocking** the main thread.

---

## **1. Callbacks**
**Definition:** Functions passed as arguments to other functions and executed later.

###  Syntax:
```javascript
function fetchData(callback) {
  setTimeout(() => {
    console.log("Data fetched!");
    callback();
  }, 2000);
}

fetchData(() => console.log("Callback executed after fetching data!"));
```
**Where to Use:**  
- When performing a task and need to execute something after it finishes.

**Drawback:**  
- Can lead to **Callback Hell** when nesting multiple callbacks.

---

## **2. Promises**
**Definition:** An object that represents the eventual completion (or failure) of an asynchronous operation.

###  Syntax:
```javascript
const promise = new Promise((resolve, reject) => {
  let success = true;
  if (success) {
    resolve("Data fetched successfully!");
  } else {
    reject("Failed to fetch data.");
  }
});

promise
  .then(response => console.log(response))
  .catch(error => console.error(error));
```
**Where to Use:**  
- Handling asynchronous tasks like API calls.

---

## **3. async/await**
**Definition:** A modern way to write asynchronous code in a synchronous style using `async` and `await` keywords.

###  Syntax:
```javascript
async function getData() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}

getData();
```
**Where to Use:**  
- Cleaner and easier to read compared to Promises.

---

## **4. XHR (XMLHttpRequest)**
**Definition:** A legacy object used to make HTTP requests to servers.

###  Example:
```javascript
const xhr = new XMLHttpRequest();
xhr.open("GET", "https://jsonplaceholder.typicode.com/posts/1");
xhr.onload = () => {
  console.log(JSON.parse(xhr.responseText));
};
xhr.send();
```
**Why Avoid:**  
- Old method; prefer Fetch API.

---

## **5. Fetch API**
**Definition:** A modern way to make HTTP requests. Returns a Promise.

###  Example:
```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
```
**Where to Use:**  
- Fetching data from APIs in web applications.

---

## **6. AJAX (Asynchronous JavaScript and XML)**
**Definition:** Technique for updating parts of a webpage without reloading the whole page. Achieved using **XHR** or **Fetch API**.

**Modern Use:**  
- Done using Fetch API or libraries like Axios.

---

### Best Practices:
- Use `fetch` or `async/await` for cleaner code.
- Handle errors using `try...catch` or `.catch()`.
- Avoid callback hell by using Promises or async/await.
