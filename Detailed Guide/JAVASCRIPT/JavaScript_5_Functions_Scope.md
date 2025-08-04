# Functions and Scope (JavaScript ES6)

Functions allow you to **organize code into reusable blocks**, and scope determines **where variables can be accessed**.

---

## **1. Function Declarations**

**Definition:** Functions declared using the `function` keyword. These are **hoisted**, meaning they can be called before they are defined in code.

### Syntax:

```javascript
function greet() {
  console.log("Hello, World!");
}
greet();
```

**Where to Use:**

- When you need reusable logic like calculations, form validations, etc.

---

## **2. Function Expressions**

**Definition:** Functions assigned to variables. These are **not hoisted**, so they must be defined before calling.

### Syntax:

```javascript
const greet = function () {
  console.log("Hello from function expression!");
};
greet();
```

**Where to Use:**

- When you want to create anonymous functions and assign them to variables.

---

## **3. Arrow Functions (ES6)**

**Definition:** A more concise way to write functions. They do not have their own `this` keyword (useful in callbacks).

### Syntax:

```javascript
const greet = () => {
  console.log("Hello from arrow function!");
};
greet();
```

**Short form for one-liner:**

```javascript
const add = (a, b) => a + b;
console.log(add(2, 3)); // 5
```

**Where to Use:**

- In callbacks and array methods like `map()`, `forEach()`, etc.

---

## **4. Scope**

**Definition:** Scope determines where variables can be accessed.

### Types of Scope:

- **Global Scope:** Variables declared outside of any function are accessible everywhere.
- **Local Scope (Function Scope):** Variables declared inside a function are only accessible within that function.
- **Block Scope:** Variables declared with `let` or `const` inside `{}` are only accessible inside that block.

---

## **5. Global Scope Example**

```javascript
let globalVar = "I am global";

function showGlobal() {
  console.log(globalVar); // Accessible here
}
showGlobal();
console.log(globalVar); // Accessible here too
```

---

## **6. Local Scope Example**

```javascript
function showLocal() {
  let localVar = "I am local";
  console.log(localVar); // Works here
}
showLocal();
// console.log(localVar); // Error: localVar is not defined
```

---

## Summary of Key Points:

- Use **function declarations** for reusable named functions.
- Use **function expressions** for dynamic function assignments.
- Use **arrow functions** for concise syntax and when `this` is not needed.
- Understand **scope** to avoid variable conflicts and errors.
