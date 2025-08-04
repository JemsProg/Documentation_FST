
# HTML Text Formatting Tags – Beginner's Guide

This guide explains the most common text formatting tags in HTML, how they work, where to use them, and real examples.

---

## 1. `<h1>` to `<h6>` — Headings
**Purpose:** Define headings from `<h1>` (largest, most important) to `<h6>` (smallest).
**Where to Use:** Use for titles and headings to structure your page.
**SEO Tip:** Search engines use headings to understand page hierarchy.

###  Example:
```html
<h1>Main Title of Page</h1>
<h2>Section Heading</h2>
<h3>Sub-section Heading</h3>
```
**Best Practice:** Only one `<h1>` per page. Use headings in order.

---

## 2. `<p>` — Paragraph
**Purpose:** Represents a block of text as a paragraph.
**Where to Use:** Wrap normal text content inside `<p>` tags.

###  Example:
```html
<p>This is a paragraph of text.</p>
```

---

## 3. `<br>` — Line Break
**Purpose:** Inserts a line break without starting a new paragraph.
**Where to Use:** Use for short breaks in text like addresses or poems.

###  Example:
```html
<p>Address:<br>123 Main Street<br>City, Country</p>
```

---

## 4. `<hr>` — Horizontal Rule
**Purpose:** Creates a horizontal line to separate sections.
**Where to Use:** Divide sections visually.

###  Example:
```html
<p>Introduction</p>
<hr>
<p>Next Section</p>
```

---

## 5. `<b>` — Bold Text
**Purpose:** Makes text bold without semantic meaning.
**Where to Use:** For visual emphasis only.

###  Example:
```html
<p>This is a <b>bold word</b>.</p>
```

---

## 6. `<strong>` — Important Text
**Purpose:** Makes text bold and semantically important for SEO and accessibility.
**Where to Use:** For critical or important words.

###  Example:
```html
<p>Please <strong>read this carefully</strong>.</p>
```

---

## 7. `<i>` — Italic Text
**Purpose:** Displays text in italics (visual styling only).
**Where to Use:** For stylistic text, foreign words, etc.

###  Example:
```html
<p>This word is <i>italicized</i>.</p>
```

---

## 8. `<em>` — Emphasized Text
**Purpose:** Displays text in italics and adds semantic emphasis.
**Where to Use:** When emphasis changes the meaning.

###  Example:
```html
<p>I said <em>do not touch</em> that button!</p>
```

---

## 9. `<u>` — Underlined Text
**Purpose:** Underlines text.
**Where to Use:** Rarely—avoid confusion with links.

###  Example:
```html
<p>This is an <u>underlined</u> word.</p>
```

---

###  When to Use Which?
- Prefer semantic tags (`<strong>`, `<em>`) over purely visual tags (`<b>`, `<i>`).
- Use CSS for styling whenever possible.
