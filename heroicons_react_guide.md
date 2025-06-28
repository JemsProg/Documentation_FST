# 📦 Heroicons in React (for Beginners)

Heroicons is a popular set of SVG icons designed by the Tailwind CSS team. These icons are easy to use in React projects, especially for modern UI applications like e-commerce systems.

---

## ✅ What You'll Learn

- How to install Heroicons in React
- How to use Outline icons from the `/24/outline` set
- Example usage with TailwindCSS

---

## 📥 Installation

In your terminal, inside your React project directory, run:

```bash
npm install @heroicons/react
```

---

## 📚 Importing an Icon

After installing, you can import specific icons from the `@heroicons/react/24/outline` path.

### Example: Shopping Cart Icon

```jsx
import { ShoppingCartIcon } from '@heroicons/react/24/outline';

function Header() {
  return <ShoppingCartIcon className="h-6 w-6 text-gray-700" />;
}
```

### Explanation:

- `h-6 w-6`: Sets the icon size (height & width to 1.5rem)
- `text-gray-700`: Sets the color using Tailwind's text color utility

---

## 🗂 Common Icons You Might Use

| Icon Purpose   | Import Name                 |
| -------------- | --------------------------- |
| Shopping Cart  | `ShoppingCartIcon`          |
| User Profile   | `UserIcon`                  |
| Logout Button  | `ArrowRightOnRectangleIcon` |
| Dashboard/Home | `HomeIcon`                  |
| Search Bar     | `MagnifyingGlassIcon`       |

---

## 🔗 Official Website

Visit the full list of icons here: 👉 [https://heroicons.com](https://heroicons.com)

Click on an icon to get the import path and usage code.

---

## 🧠 Tips for Beginners

- Always choose from `@heroicons/react/24/outline` for outline icons.
- Use `className` to style icons using TailwindCSS.
- These icons are React components, so you can treat them like any JSX element.

---

You're now ready to use Heroicons in your React app! 🚀

