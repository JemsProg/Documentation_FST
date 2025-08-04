
#  Other Useful HTML Tags – Beginner's Guide

These tags are not semantic but are widely used for grouping and styling elements in HTML. They are often used with CSS and JavaScript.

---

## 1. `<span>` — Inline Container
**Purpose:** Acts as an inline container for text or other inline elements.
**Where to Use:** When you need to style or manipulate a portion of text within a line without breaking it into a new block.

###  Syntax:
```html
<span>Text here</span>
```

###  Attributes:
- Common attributes like `class`, `id`, and `style` can be used to apply CSS.

###  Example:
```html
<p>This is <span style="color:red">important text</span> inside a paragraph.</p>
```

**Real Use Case:**
- Highlight specific words in a sentence.
- Apply special styling to certain words.

---

## 2. `<div>` — Block-Level Container
**Purpose:** A block-level container used to group multiple elements together.
**Where to Use:** When you need to group content for layout, styling, or scripting.

###  Syntax:
```html
<div>
  <p>This is inside a div.</p>
</div>
```

###  Attributes:
- Common attributes like `class`, `id`, and `style` for CSS styling and JS manipulation.

###  Example:
```html
<div style="background-color:lightblue; padding:10px;">
  <h2>Welcome</h2>
  <p>This is a grouped section inside a div.</p>
</div>
```

**Real Use Case:**
- Page layout sections (e.g., header, footer, sidebar, content area).
- Grouping multiple elements for styling or scripts.

---

##  Differences Between `<div>` and `<span>`:
- `<div>` is **block-level**: starts on a new line and takes up the full width.
- `<span>` is **inline**: stays in line with surrounding text.

---

##  Complete Example Using Both:
```html
<div style="border:1px solid black; padding:10px;">
  <h3>Article Title</h3>
  <p>This paragraph has a <span style="color:red;">highlighted word</span>.</p>
</div>
```

---

###  Best Practices:
- Use `<div>` for larger sections of content.
- Use `<span>` for small inline changes.
- For better **SEO and accessibility**, prefer **semantic tags** like `<header>`, `<section>` when possible.
