# HTML Tables – Beginner's Guide

Tables are used in HTML to display data in **rows and columns**. They are helpful for organizing structured data.

---

## 1. `<table>` — Table Container

**Purpose:** Defines the start and end of a table.
**Where to Use:** Use whenever you need to organize data into rows and columns.

### Syntax:

```html
<table>
  <!-- Table rows and cells go here -->
</table>
```

**Example in Real Project:**

- Product price lists
- Student grades table
- Timetables

---

## 2. `<tr>` — Table Row

**Purpose:** Defines a row inside a table.
**Where to Use:** Inside a `<table>` to group cells horizontally.

### Syntax:

```html
<tr>
  <td>Row 1, Column 1</td>
  <td>Row 1, Column 2</td>
</tr>
```

---

## 3. `<td>` — Table Data Cell

**Purpose:** Defines a data cell in the table (normal content).
**Where to Use:** Inside a `<tr>`.

### Syntax:

```html
<td>Data</td>
```

**Example:**

```html
<table border="1">
  <tr>
    <td>Apple</td>
    <td>$1</td>
  </tr>
</table>
```

---

## 4. `<th>` — Table Header Cell

**Purpose:** Defines a header cell (usually bold and centered by default).
**Where to Use:** Inside a `<tr>` at the top of the table or start of rows.

### Syntax:

```html
<th>Header Name</th>
```

**Example:**

```html
<table border="1">
  <tr>
    <th>Product</th>
    <th>Price</th>
  </tr>
  <tr>
    <td>Apple</td>
    <td>$1</td>
  </tr>
</table>
```

---

## Complete Example:

```html
<h3>Product Price Table</h3>
<table border="1">
  <tr>
    <th>Product</th>
    <th>Price</th>
  </tr>
  <tr>
    <td>Apple</td>
    <td>$1</td>
  </tr>
  <tr>
    <td>Banana</td>
    <td>$0.50</td>
  </tr>
</table>
```

---

### Attributes for `<table>`:

- `border` – Adds a border around the table (e.g., `border="1"`).
- `cellpadding` – Adds space inside cells.
- `cellspacing` – Adds space between cells.
  _(Note: For modern design, use CSS instead of these attributes.)_

---

### Best Practices:

- Use `<th>` for headers to improve accessibility and readability.
- Avoid using tables for page layout; use **CSS grid or flexbox** for layout purposes.
