# 📦 How to Install Axios (Beginner-Friendly Guide)

When building a React (or other JavaScript) app, you often need to send HTTP requests to your backend or APIs.  
**Axios** is a popular library that makes it easy to send those requests.

Here’s **what Axios is, and how to install it step by step!**

---

## ❓ What is Axios?

✅ **Axios** is a JavaScript library that lets you make HTTP requests to your server or APIs.  
You can use it to:
- Get data (`GET` request)
- Send data (`POST` request)
- Update or delete data

It works in the browser and in Node.js.

---

## 🔷 How to Install Axios

### ✅ Step 1: Open Your Project Folder

Make sure you’re inside your React (or other Node.js) project folder in the terminal.

You should see something like this in your folder:
```
package.json
src/
public/
node_modules/
```

---

### ✅ Step 2: Run the Install Command

In your terminal, type:

```bash
npm install axios
```

This will download Axios and add it to your `node_modules` folder.

✅ You’ll see something like:
```
+ axios@1.x.x
added 1 package
```

---

### ✅ Step 3: Verify Installation

Check your `package.json` file. Under `dependencies`, you should see:
```json
"dependencies": {
  "axios": "^1.x.x",
  ...
}
```

---

### 🔷 How to Use Axios (Quick Example)

In your React component:

```jsx
import axios from 'axios';

function getProducts() {
  axios.get('/api/products/')
    .then(response => {
      console.log(response.data);
    })
    .catch(error => {
      console.error(error);
    });
}
```

---

## 🏁 Summary: What & How

✅ **What is Axios?**
- A library to send HTTP requests from JavaScript apps.

✅ **How to install it?**
1. Open your project folder in the terminal.
2. Run: `npm install axios`
3. Check that it’s added to `package.json`.

🎉 That’s it — Axios is ready to use in your project!

🔗 Learn more: [https://axios-http.com/](https://axios-http.com/)
