# DOM Manipulation (JavaScript for Beginners)

DOM (Document Object Model) manipulation is how JavaScript interacts with HTML and CSS to create dynamic web pages. This is essential for building interactive websites.

---

## **1. What is the DOM?**

**Definition:** The DOM represents the structure of an HTML document as a tree of objects. JavaScript can access and modify this tree to change content, styles, or structure.

**Why Important?**

- It allows you to **update the page without reloading**.
- Essential for creating **interactive UI elements**.

---

## **2. Selecting Elements**

JavaScript provides multiple methods to select HTML elements.

### Common Methods:

- `document.getElementById("id")` – Selects by ID.
- `document.querySelector("selector")` – Selects the first element that matches a CSS selector.
- `document.querySelectorAll("selector")` – Selects all matching elements.

### Example:

```html
<h1 id="title">Hello</h1>
<script>
  const heading = document.getElementById("title");
  console.log(heading.textContent); // Hello
</script>
```

**Where to Use:**

- Selecting elements to change text, add styles, or attach event listeners.

---

## **3. Changing Text and HTML**

- `element.textContent` – Changes text only.
- `element.innerHTML` – Changes HTML content.

### Example:

```html
<p id="message">Welcome!</p>
<script>
  const message = document.querySelector("#message");
  message.textContent = "Hello, JavaScript!"; // Changes text
</script>
```

---

## **4. Changing CSS Styles**

Modify CSS using the `style` property or by adding/removing classes.

### Example:

```html
<h2 id="heading">Change My Color</h2>
<script>
  const heading = document.getElementById("heading");
  heading.style.color = "blue"; // Inline CSS change
</script>
```

---

## **5. Adding and Removing Classes**

Use `classList` for dynamic class changes.

### Example:

```html
<div id="box" class="red-box"></div>
<script>
  const box = document.getElementById("box");
  box.classList.add("highlight"); // Add a class
  box.classList.remove("red-box"); // Remove a class
</script>
```

---

## **6. Creating and Adding Elements**

Use `createElement()` and `appendChild()` to add new elements dynamically.

### Example:

```html
<ul id="list"></ul>
<script>
  const list = document.getElementById("list");
  const newItem = document.createElement("li");
  newItem.textContent = "New Item";
  list.appendChild(newItem);
</script>
```

**Where to Use:**

- Adding new tasks in a to-do app.
- Adding new comments dynamically.

---

## **7. Removing Elements**

Use `removeChild()` or `element.remove()`.

### Example:

```html
<ul id="list">
  <li>Item 1</li>
  <li id="item2">Item 2</li>
</ul>
<script>
  const item2 = document.getElementById("item2");
  item2.remove(); // Removes Item 2
</script>
```

---

## **8. Practical Example: To-Do List**

```html
<h3>To-Do List</h3>
<input type="text" id="taskInput" placeholder="Enter task" />
<button id="addBtn">Add Task</button>
<ul id="taskList"></ul>

<script>
  const addBtn = document.getElementById("addBtn");
  const taskInput = document.getElementById("taskInput");
  const taskList = document.getElementById("taskList");

  addBtn.addEventListener("click", () => {
    const taskText = taskInput.value;
    if (taskText.trim() !== "") {
      const li = document.createElement("li");
      li.textContent = taskText;
      taskList.appendChild(li);
      taskInput.value = "";
    }
  });
</script>
```

---

### Best Practices:

- Use `querySelector()` for flexible selections.
- Avoid heavy DOM manipulation inside loops (use fragments or batch updates).
- Keep HTML structure clean for easier DOM access.
