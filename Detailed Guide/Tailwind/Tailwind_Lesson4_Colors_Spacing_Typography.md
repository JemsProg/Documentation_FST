# Tailwind CSS v4.1 - Lesson 4: Colors, Spacing & Typography

Tailwind provides a wide range of utility classes for **colors**, **spacing**, and **typography**, making it easy to create visually consistent designs.

---

## **1. Colors in Tailwind**

Tailwind has a built-in color palette using **color names + shade numbers** (e.g., `blue-500`, `gray-200`).  
The number represents **intensity** (100 = light, 900 = dark).

### Background Colors

```html
<div class="bg-blue-500 text-white p-4">Blue Background</div>
<div class="bg-gray-200 p-4">Gray Background</div>
```

### Text Colors

```html
<p class="text-red-500">This is red text.</p>
<p class="text-green-700">This is green text.</p>
```

### Border Colors

```html
<div class="border-4 border-purple-500 p-4">Purple Border</div>
```

---

## **2. Spacing in Tailwind**

Tailwind uses a **spacing scale** for padding, margin, gap, etc.  
Example values: `0, 1, 2, 4, 6, 8, 10, 12` (each equals `0.25rem` × value).

### Padding

```html
<div class="p-4 bg-yellow-200">Padding on all sides</div>
<div class="px-6 py-2 bg-green-200">Horizontal and Vertical Padding</div>
```

### Margin

```html
<div class="m-4 bg-gray-200">Margin on all sides</div>
<div class="mt-8 mb-4 bg-gray-300">Margin top & bottom</div>
```

### Gap (For Flex/Grid)

```html
<div class="flex gap-4">
  <div class="bg-blue-300 p-4">Item 1</div>
  <div class="bg-blue-300 p-4">Item 2</div>
</div>
```

---

## **3. Typography in Tailwind**

Tailwind offers utilities for **font size**, **weight**, **line height**, and **letter spacing**.

### Font Size

```html
<p class="text-sm">Small Text</p>
<p class="text-lg">Large Text</p>
<p class="text-4xl">Extra Large Text</p>
```

### Font Weight

```html
<p class="font-light">Light Text</p>
<p class="font-bold">Bold Text</p>
```

### Line Height & Letter Spacing

```html
<p class="leading-relaxed tracking-wide">
  Tailwind makes typography easy and clean.
</p>
```

---

## Combining Colors, Spacing, and Typography

Example:

```html
<div class="bg-indigo-500 text-white text-xl font-bold p-6 rounded shadow-lg">
  Tailwind is powerful and easy to use!
</div>
```

✔ Background color → `bg-indigo-500`  
✔ Text color → `text-white`  
✔ Font size & weight → `text-xl font-bold`  
✔ Padding → `p-6`  
✔ Rounded corners & shadow → `rounded shadow-lg`

---

### Key Takeaways

✔ Tailwind uses **color + shade** system (e.g., `blue-500`).  
✔ Spacing uses a **scale** (e.g., `p-4`, `m-6`).  
✔ Typography utilities handle **size, weight, line height** without custom CSS.

---
