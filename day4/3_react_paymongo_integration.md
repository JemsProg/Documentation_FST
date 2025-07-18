# 🧾 React Integration for PayMongo GCash Checkout

This guide walks you through integrating the **frontend logic** in React for the GCash checkout using PayMongo. It assumes your Django backend (already documented) is running and configured.

---

## ✅ Features Covered

- Display cart and total cost
- Trigger checkout
- Collect user shipping details
- Redirect to PayMongo checkout link

---

## 📦 1. Update Cart Page: `Cart.jsx`

This page:

- Fetches cart items from backend
- Shows total/subtotal
- Stores subtotal to `localStorage` for checkout

### ✨ Updated Checkout Button Logic:

```jsx
<button
  onClick={() => {
    localStorage.setItem("subtotal", subtotal.toFixed(2));
    navigate("/shipping-details");
  }}
  className="w-full mt-6 bg-indigo-600 text-white py-2 rounded hover:bg-indigo-700 text-base font-medium"
>
  Checkout
</button>
```

> This saves the subtotal temporarily and navigates to the shipping form.

---

## 📝 2. Create `ShippingDetails.jsx`

This is the page where users enter their name, email, address, etc. It sends a POST request to your backend Django API (`/api/payments/create/`) and receives a **PayMongo checkout URL**.

### ✨ Full Component:

```jsx
import React, { useState } from "react";
import axios from "axios";
import { BASE_URL } from "../api/AuthApi";

const ShippingDetails = () => {
  const [formData, setFormData] = useState({
    full_name: "",
    address: "",
    city: "",
    postal_code: "",
    country: "",
    email: "",
    mobile: "",
  });

  const [error, setError] = useState("");
  const subtotal = localStorage.getItem("subtotal") || 0;

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleCheckout = async () => {
    try {
      const token = localStorage.getItem("access_token");
      const res = await axios.post(
        `${BASE_URL}api/payments/create/`,
        {
          ...formData,
          total_price: parseFloat(subtotal),
        },
        {
          headers: {
            Authorization: `Bearer ${token}`,
          },
        }
      );

      if (res.data.checkout_url) {
        window.location.href = res.data.checkout_url;
      } else {
        setError("Failed to create payment link.");
      }
    } catch (err) {
      console.error(err);
      setError("Something went wrong.");
    }
  };

  return (
    <div className="max-w-lg mx-auto p-4">
      <h2 className="text-xl font-semibold mb-4">Shipping Details</h2>
      {["full_name", "address", "city", "postal_code", "country", "email", "mobile"].map((field) => (
        <input
          key={field}
          name={field}
          placeholder={field.replace("_", " ").toUpperCase()}
          value={formData[field]}
          onChange={handleChange}
          className="w-full mb-3 p-2 border rounded"
          required
        />
      ))}
      {error && <p className="text-red-600">{error}</p>}
      <button
        onClick={handleCheckout}
        className="w-full bg-indigo-600 text-white py-2 rounded hover:bg-indigo-700"
      >
        Pay with GCash
      </button>
    </div>
  );
};

export default ShippingDetails;
```

> 🔐 Make sure user is authenticated using token in `localStorage`

---

## 🛣 3. Update Your `App.jsx` Routes

Import the component and add route:

```jsx
import ShippingDetails from "./pages/ShippingDetails";

<Routes>
  <Route path="/shipping-details" element={<ShippingDetails />} />
</Routes>
```

---

## 🧪 Testing the Flow

1. Add products to cart
2. Go to `/cart` and click **Checkout**
3. Fill out `/shipping-details` form
4. User is redirected to PayMongo checkout
5. After payment, backend webhook will confirm and store order

---

## ✅ Summary

- Cart page collects subtotal and redirects to shipping
- Shipping page collects details and triggers payment
- Payment is created in backend and PayMongo returns the URL
- Frontend redirects user to PayMongo

You're now fully integrated on the frontend side 🎉

---

👉 Proceed to testing webhook and order creation confirmation!

