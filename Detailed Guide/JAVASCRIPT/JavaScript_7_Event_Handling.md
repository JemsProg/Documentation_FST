
#  Event Handling (JavaScript ES6)

Event handling in JavaScript allows you to make web pages interactive by responding to user actions like clicks, typing, or form submissions.

---

## **1. Events**
**Definition:** Actions that happen as a result of user interactions or other triggers.

###  Examples of Events:
- `click` – When a user clicks an element.
- `keyup` / `keydown` – When a key is pressed or released.
- `submit` – When a form is submitted.
- `mouseover` – When the mouse hovers over an element.

---

## **2. Event Handlers**
**Definition:** Functions that are executed when an event occurs.

###  Example:
```html
<button onclick="alert('Button Clicked!')">Click Me</button>
```

**Where to Use:**  
- Quick inline event handling for simple tasks (not recommended for large apps).

---

## **3. Event Listeners**
**Definition:** A modern way to handle events using `addEventListener()`.

###  Syntax:
```javascript
element.addEventListener("event", function);
```

###  Example:
```javascript
const btn = document.querySelector("#myButton");

btn.addEventListener("click", () => {
  alert("Button clicked using addEventListener!");
});
```
**Where to Use:**  
- Preferred way to attach events in modern JavaScript.

---

## **4. Event Object**
**Definition:** When an event occurs, an event object is automatically passed to the handler, containing details about the event.

###  Example:
```javascript
document.querySelector("#myButton").addEventListener("click", (event) => {
  console.log("Event type:", event.type); // click
  console.log("Clicked element:", event.target);
});
```

**Where to Use:**  
- Get information like which element was clicked or what key was pressed.

---

## **5. Event Propagation**
**Definition:** The order in which event handlers run:
- **Capturing Phase:** Events go from the root (document) down to the target.
- **Bubbling Phase:** Events bubble up from the target to the root.

###  Example:
```javascript
document.querySelector("#parent").addEventListener("click", () => {
  console.log("Parent clicked!");
});

document.querySelector("#child").addEventListener("click", () => {
  console.log("Child clicked!");
});
```
Clicking the child will trigger **both** (child first, then parent).

**Where to Use:**  
- When handling nested elements.

---

## **6. Event Delegation**
**Definition:** A technique to handle events on multiple child elements using one event listener on their parent.

###  Example:
```javascript
document.querySelector("#list").addEventListener("click", (event) => {
  if (event.target.tagName === "LI") {
    console.log("Clicked item:", event.target.textContent);
  }
});
```
**Why Use:** Improves performance when you have many elements.

---

###  Best Practices:
- Use `addEventListener()` instead of inline event handlers.
- Remove event listeners when no longer needed to avoid memory leaks.
- Use **event delegation** for dynamic lists or large sets of elements.
