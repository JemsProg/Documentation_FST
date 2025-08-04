
#  Introduction to JavaScript (ES6)

JavaScript is one of the most popular programming languages used to add **interactivity** and **dynamic behavior** to web pages.

---

## **1. What is JavaScript?**
JavaScript is a **high-level, interpreted programming language** used for:
- Adding interactivity to web pages.
- Manipulating HTML and CSS dynamically.
- Building web applications (React, Angular, etc.).

###  Example:
```html
<button onclick="alert('Hello!')">Click Me</button>
```

---

## **2. Variables**
Variables are containers for storing data.

In **ES6**, use:
- `let` → For values that can change.
- `const` → For values that should NOT change.
- Avoid `var` (old way, has issues with scope).

###  Example:
```javascript
let name = "John";  // can be reassigned
const age = 25;     // cannot be changed
```

**Where to Use:**
- `let` for loops, counters, or changing values.
- `const` for fixed values like API URLs.

---

## **3. Data Types**
JavaScript supports several data types:

| Type    | Example |
|---------|---------|
| Number  | `let age = 30;` |
| String  | `let name = "Alice";` |
| Boolean | `let isLoggedIn = true;` |
| Array   | `let colors = ["red", "blue"];` |
| Object  | `let user = {name:"Tom", age:22};` |

###  Example:
```javascript
const user = {
  name: "Alice",
  age: 25,
  hobbies: ["reading", "coding"]
};
console.log(user.name); // Alice
```

---

## **4. Operators**
Operators allow you to perform actions on values.

- **Arithmetic:** `+`, `-`, `*`, `/`, `%`
- **Comparison:** `==`, `===`, `!=`, `!==`, `<`, `>`
- **Logical:** `&&`, `||`, `!`

###  Example:
```javascript
let a = 10, b = 5;
console.log(a + b);   // 15
console.log(a > b);   // true
console.log(a === b); // false
```

---

## **5. Functions**
Functions are blocks of code that perform a specific task.

###  Two Ways to Write Functions in ES6:
#### Normal Function:
```javascript
function greet() {
  console.log("Hello, World!");
}
greet();
```

#### Arrow Function (ES6):
```javascript
const greet = () => {
  console.log("Hello, World!");
};
greet();
```

**Where to Use:**
- Reusable tasks like calculations or form validation.

---

###  Summary:
- Use **JavaScript** to make websites interactive.
- Use **`let` and `const`** for variables.
- Understand **data types** and **operators**.
- Create **functions** for reusable code.
