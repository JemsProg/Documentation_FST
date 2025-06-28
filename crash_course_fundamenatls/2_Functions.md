# JavaScript Functions

This section covers **functions** in JavaScript — reusable blocks of code that perform a specific task. We'll look at both **regular functions** and **arrow functions**, how to pass **parameters**, and how to use **return** values.

---

## ✅ What is a Function?

A function is a set of statements that performs a task or calculates a value. You can **call** (run) a function whenever you want.

### Example (Regular Function):

```js
function greet(name) {
  return "Hello " + name;
}

console.log(greet("Jems")); // Output: Hello Jems
```

- `greet` is the function name.
- `name` is the parameter (input).
- `return` sends back a value.
- `"Hello " + name` is the logic being executed.

---

## ⚡ Arrow Functions (ES6)

Arrow functions are a shorter way to write functions. They are especially useful for **simple logic**.

### Example (Arrow Function):

```js
const add = (a, b) => a + b;

console.log(add(2, 3)); // Output: 5
```

This is equivalent to:

```js
function add(a, b) {
  return a + b;
}
```

---

## 🧠 Key Differences

| Feature        | Regular Function           | Arrow Function                 |
| -------------- | -------------------------- | ------------------------------ |
| Syntax         | Verbose                    | Short & clean                  |
| `this` Binding | Dynamic (based on context) | Lexical (inherits from parent) |
| Use Case       | Best for complex logic     | Best for simple one-liners     |

---

## ✅ Summary

- Use regular functions for flexible or complex tasks.
- Use arrow functions when writing simple logic or callbacks.
- Functions can return values and accept parameters.

---

Practice writing your own functions like:

```js
const multiply = (x, y) => x * y;
const sayHello = (name) => `Hi, ${name}!`;
```

🕒 Spend a few minutes testing your own functions in the console!
