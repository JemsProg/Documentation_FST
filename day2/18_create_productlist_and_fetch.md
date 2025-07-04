# 🖥️ How to Create `ProductList.jsx` and Fetch Data from Django (Beginner-Friendly Guide)

When building a React frontend and a Django backend, you often need to **fetch data from Django and display it in React**.  
Here’s **what this code does, and how to use it step by step!**

---

## ❓ What Does This Do?

✅ The code below:
- Creates a `ProductList.jsx` component.
- Sends a `GET` request to your Django API endpoint: `/api/products/`.
- Saves the data in state and displays it in the browser.

---

## 🔷 How to Do It

### ✅ Step 1: Install Axios

If you haven’t already, install Axios in your React project:

```bash
npm install axios
```

---

### ✅ Step 2: Create `ProductList.jsx`

Inside your React `src/components/` folder, create a file named:

📄 `ProductList.jsx`

---

### ✅ Step 3: Write the Component

Here’s the code:

```jsx
import { useEffect, useState } from "react";
import axios from "axios";

function ProductList() {
  const [products, setProducts] = useState([]);

  useEffect(() => {
    axios.get("http://127.0.0.1:8000/api/products/")
      .then((res) => {
        setProducts(res.data);
      })
      .catch((err) => {
        console.error(err);
      });
  }, []);

  return (
    <div>
      <h2>Product List</h2>
      <ul>
        {products.map((product) => (
          <li key={product.id}>
            {product.name} - ${product.price}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default ProductList;
```

---

## 🔷 How It Works

✅ Step-by-step explanation:
1️⃣ `useState([])` → Starts with an empty list of products.  
2️⃣ `useEffect()` → Runs after the component loads.  
3️⃣ `axios.get()` → Sends a request to your Django backend.  
4️⃣ `setProducts(res.data)` → Saves the response data into state.  
5️⃣ `.map()` → Loops over the products and displays them in a list.

---

## 🔷 Example Output

If your Django backend returns:
```json
[
  { "id": 1, "name": "T-Shirt", "price": "19.99" },
  { "id": 2, "name": "Shoes", "price": "49.99" }
]
```

Your React app will display:
```
Product List
- T-Shirt - $19.99
- Shoes - $49.99
```

---

## 🏁 Summary: What & How

✅ **What does it do?**
- Fetches product data from Django and shows it in React.

✅ **How to set it up?**
1. Install Axios: `npm install axios`.
2. Create `ProductList.jsx` with `useEffect` and `axios.get()`.
3. Display the data with `.map()`.

🎉 That’s it — your React component is now fetching live data from Django!

🔗 Learn more: [https://axios-http.com/](https://axios-http.com/)
