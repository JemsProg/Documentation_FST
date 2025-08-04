# HTML Lists – Beginner's Guide

Lists are used in HTML to group related items together. They make content easier to read and organize.

---

## 1. `<ul>` — Unordered List

**Purpose:** Creates a list of items where the order does not matter. Items are displayed with **bullets** by default.
**Where to Use:** For menus, feature lists, or any collection of items where order is not important.

### Syntax:

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

### ✅ Example in Real Project:

- Navigation menus
- Lists of benefits or features on a landing page

```html
<h3>Features:</h3>
<ul>
  <li>Fast Performance</li>
  <li>User-Friendly Interface</li>
  <li>Secure Transactions</li>
</ul>
```

---

## 2. `<ol>` — Ordered List

**Purpose:** Creates a list of items where **order matters**. Items are numbered by default.
**Where to Use:** For instructions, rankings, or steps in a process.

### Syntax:

```html
<ol>
  <li>Step 1</li>
  <li>Step 2</li>
  <li>Step 3</li>
</ol>
```

### Example in Real Project:

- How-to guides
- Recipe steps
- Numbered rankings

```html
<h3>Steps to Register:</h3>
<ol>
  <li>Enter your email address</li>
  <li>Create a password</li>
  <li>Click the Sign-Up button</li>
</ol>
```

**Attributes for `<ol>`:**

- `type` – Changes numbering style (e.g., `type="A"` for letters).
- `start` – Sets starting number (e.g., `start="5"`).

Example:

```html
<ol type="A" start="3">
  <li>Third option</li>
  <li>Fourth option</li>
</ol>
```

---

## 3. `<li>` — List Item

**Purpose:** Defines each item inside `<ul>` or `<ol>`.
**Where to Use:** Always inside `<ul>` or `<ol>`.

### Syntax:

```html
<li>Item</li>
```

### Example:

```html
<ul>
  <li>Home</li>
  <li>About</li>
  <li>Contact</li>
</ul>
```

---

### Best Practices:

- Use `<ul>` for unordered items (e.g., navigation menus).
- Use `<ol>` for ordered sequences (e.g., steps in a guide).
- Each list item must be inside `<li>`.

---
