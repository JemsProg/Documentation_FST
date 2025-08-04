# Tailwind CSS v4.1 - Lesson 2 (Part 3): Adding Tailwind Directives & Testing Tailwind

After installing Tailwind (via **Vite** or **CRA**), we need to **activate Tailwind styles** and verify the setup.

---

## **1. Adding Tailwind Directives**

Tailwind uses **three special CSS directives** to include its core layers:

- `@tailwind base;` → Adds browser reset and base styles.
- `@tailwind components;` → Adds pre-designed component classes.
- `@tailwind utilities;` → Adds all utility classes (like `bg-red-500`, `p-4`, etc.).

Open `src/index.css` (or `src/global.css`) and replace its content with:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

This ensures Tailwind’s styles are available in your app.

---

## **2. Import index.css in Your Entry File**

Ensure the main entry file imports the CSS:

- **For Vite** → `main.jsx`

```javascript
import "./index.css";
```

- **For CRA** → `index.js`

```javascript
import "./index.css";
```

---

## **3. Test if Tailwind Works**

Now let’s confirm everything is working by applying a Tailwind class.

Open `App.jsx` (or `App.js`) and replace its content with:

```javascript
function App() {
  return (
    <div className="flex items-center justify-center h-screen bg-red-500">
      <h1 className="text-4xl font-bold text-white">Tailwind is Working!</h1>
    </div>
  );
}

export default App;
```

### Expected Output:

✔ The background should be **red** (`bg-red-500`).  
✔ Text should be **white, bold, and large**.  
✔ Content should be **centered** vertically and horizontally.

---

## **4. Start the Development Server**

Run your app:

- **For Vite**:

```bash
npm run dev
```

- **For CRA**:

```bash
npm start
```

Open the local URL in your browser. If you see a **full red screen with text**, Tailwind is working! 🎉

---

## Troubleshooting

✔ Make sure `@tailwind` directives are added in `index.css`.  
✔ Ensure `index.css` is imported in your entry file.  
✔ Restart the dev server after installation.

---

### Summary

✔ Added Tailwind directives (`@tailwind base; @tailwind components; @tailwind utilities;`).  
✔ Verified setup by applying **bg-red-500** to a div.  
✔ Tailwind is now fully functional in your project.

---
