# Tailwind CSS v4.1 - Lesson 5: Layout Basics (Flexbox, Grid, Positioning)

Tailwind makes creating layouts easy using **Flexbox**, **Grid**, and **Positioning utilities**.

---

## **1. Flexbox in Tailwind**

Flexbox helps arrange items in rows or columns with easy alignment.

### Enable Flex

```html
<div class="flex bg-gray-200 p-4">
  <div class="bg-blue-400 p-2">Item 1</div>
  <div class="bg-green-400 p-2">Item 2</div>
</div>
```

### Direction

- `flex-row` → Horizontal (default)
- `flex-col` → Vertical

```html
<div class="flex flex-col gap-2 bg-gray-200 p-4">
  <div class="bg-blue-400 p-2">Item 1</div>
  <div class="bg-green-400 p-2">Item 2</div>
</div>
```

### Alignment

- `justify-center` → Horizontal center
- `items-center` → Vertical center

```html
<div class="flex justify-center items-center h-40 bg-gray-300">
  <div class="bg-blue-500 text-white p-4">Centered</div>
</div>
```

---

## **2. Grid in Tailwind**

Grid helps create multi-column layouts easily.

### Basic Grid

```html
<div class="grid grid-cols-3 gap-4 p-4 bg-gray-200">
  <div class="bg-blue-300 p-4">1</div>
  <div class="bg-green-300 p-4">2</div>
  <div class="bg-red-300 p-4">3</div>
</div>
```

### Responsive Grid

```html
<div class="grid grid-cols-1 md:grid-cols-3 gap-4 p-4">
  <div class="bg-blue-300 p-4">1</div>
  <div class="bg-green-300 p-4">2</div>
  <div class="bg-red-300 p-4">3</div>
</div>
```

✔ 1 column on small screens, 3 columns on medium screens.

---

## **3. Positioning**

Tailwind provides utilities for absolute, relative, and fixed positioning.

### Example

```html
<div class="relative bg-gray-200 h-40">
  <div class="absolute top-2 right-2 bg-blue-500 text-white p-2">Top Right</div>
</div>
```

### z-index

```html
<div class="relative h-40 bg-gray-300">
  <div class="absolute top-4 left-4 bg-blue-500 p-2 z-10">On Top</div>
  <div class="absolute top-6 left-6 bg-red-500 p-2">Behind</div>
</div>
```

---

## Combining Layout Utilities

```html
<div class="flex flex-col md:flex-row gap-4 p-4">
  <div class="flex-1 bg-blue-300 p-4">Flex Item 1</div>
  <div class="flex-1 bg-green-300 p-4">Flex Item 2</div>
</div>
```

✔ Responsive: Changes from column to row on medium screens.

---

### Key Takeaways

✔ **Flexbox** for aligning and distributing items.  
✔ **Grid** for multi-column layouts.  
✔ **Positioning utilities** for absolute, relative, fixed elements.

---
