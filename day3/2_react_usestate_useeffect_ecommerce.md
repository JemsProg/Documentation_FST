# 🧠 React `useState` + `useEffect` Hook: What & How — E-Commerce Example

This documentation explains **what `useState` and `useEffect` are in React, how to use them**, and provides a realistic example related to an **e-commerce web system**.

---

## ❓ What is `useState`?

✅ `useState` is a **React Hook** that lets you add **state** to functional components.  
It allows your component to "remember" and "update" data as the user interacts with your app.

For example:
- Track the list of products loaded from your backend.
- Store cart items.

---

## ❓ What is `useEffect`?

✅ `useEffect` is a **React Hook** that lets you run side effects in your component.  
Side effects include things like:
- Fetching data from an API.
- Setting up event listeners.
- Updating the document title.

In an e-commerce app, we use `useEffect` to fetch the product list when the page loads.

---

## 🔷 E-Commerce Example: Product List

Here’s a realistic example of using `useState` and `useEffect` together to build a **ProductList page**.

```jsx
import React, { useState, useEffect } from "react";
import { Link } from "react-router-dom";
import axios from "axios";

const ProductList = () => {
  const [products, setProducts] = useState([]);

  useEffect(() => {
    const fetchProducts = async () => {
      try {
        const res = await axios.get("http://127.0.0.1:8000/products");
        setProducts(res.data);
      } catch (err) {
        console.error("Error fetching products:", err);
      }
    };

    fetchProducts();
  }, []);

  return (
    <div>
      <div className="flex flex-wrap justify-evenly gap-2 mt-25">
        {products.map((product, index) => (
          <div key={index} className="w-80 shadow-xl p-8">
            <Link to={`/product/${product.product_id}`}>
              <img
                src={`http://127.0.0.1:8000/${product.image}`}
                alt="product"
              />
              <span className="font-bold">{product.product_name}</span>
              <div className="flex flex-wrap justify-between text-sm">
                <p>{product.brand}</p>
                <p>${product.product_price}</p>
              </div>
            </Link>
          </div>
        ))}
      </div>
    </div>
  );
};

export default ProductList;
```

---

## 🔷 How it Works

✅ **`useState`**
- Initializes `products` as an empty array: `useState([])`.
- When the API call finishes, `setProducts()` updates the state with the fetched data.
- React re-renders the component with the new products.

✅ **`useEffect`**
- Runs the `fetchProducts` function only once when the component mounts, because of the empty dependency array (`[]`).
- Makes an HTTP GET request to `/products` using `axios`.
- Saves the response data into the `products` state.

---

## 📝 Why is this good for e-commerce?

🎯 Because you want your **product list page** to:
- Always show the latest products from your backend database.
- Dynamically render products and their details.

---

### Tips:
✅ Always use `setState` (`setProducts`) to update state — don’t mutate it directly.  
✅ Use unique `key` props for list items (preferably `product.product_id`).  
✅ Use `useEffect(() => {}, [])` to fetch data only on mount.  
✅ Use proper error handling and fallback UI if needed.

---

## 🏁 Summary: What & How

✅ **What are they?**
- `useState`: lets you create and update state in functional components.
- `useEffect`: lets you run side effects (like fetching data) when the component mounts.

✅ **How does it work in this example?**
- Fetch products from Django backend when the page loads.
- Save them in state and display them dynamically.

🎉 That’s it — you now know how to use `useState` and `useEffect` in your e-commerce React app to load and display products from your backend!

---

🔗 Learn more: [React Docs: State and Effect Hooks](https://react.dev/reference/react)
