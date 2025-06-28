# ⚙️ Installing Tools: Vite + React + Tailwind CSS v4.1 (npm Only)

## ✅ Prerequisites
Install and verify:
```bash
node -v   
npm -v    
```

---

## 🧱 Step 1: Create Vite + React App
```bash
npm create vite@latest my-ecommerce-app -- --template react
cd my-ecommerce-app
npm install
```

---

## 📦 Step 2: Install Tailwind CSS v4.1 and Dependencies
```bash
npm install -D tailwindcss@latest postcss autoprefixer
npx tailwindcss init -p
```

✅ This creates:
- `tailwind.config.js`
- `postcss.config.js`

---

## 🎨 Step 3: Configure Tailwind

**Update `tailwind.config.js`:**
```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

**Update `src/index.css`:**
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

## 🚀 Step 4: Start the Dev Server
```bash
npm run dev
```

🔗 Open in browser: [http://localhost:5173](http://localhost:5173)

---

## ✅ Done!

You now have:
- React (via Vite) for SPA development
- Tailwind CSS 4.1 with latest utility-first styling
- Live reload + HMR via Vite
