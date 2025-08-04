
#  Modern JavaScript for React: Template Literals

**Template Literals** provide an easier and cleaner way to work with strings in JavaScript.  
They allow you to **embed variables and expressions inside strings** without messy concatenation.

---

## **1. What Are Template Literals?**
- Introduced in **ES6**.
- Use **backticks (`) instead of quotes**.
- Allow **string interpolation** using `${}`.

---

###  Example: Basic Usage
```javascript
const name = "Alice";
const message = `Hello, ${name}! Welcome to React.`;
console.log(message); // Hello, Alice! Welcome to React.
```

---

## **2. Multi-line Strings**
No need for `\n` to create new lines.

```javascript
const text = `This is line one.
This is line two.`;

console.log(text);
// Output:
// This is line one.
// This is line two.
```

---

## **3. Embedding Expressions**
You can use JavaScript expressions inside `${}`.

```javascript
const a = 5;
const b = 10;
console.log(`The sum is ${a + b}`); // The sum is 15
```

---

##  **Where Used in React**
Template literals are often used for **dynamic content** and **class names** in React.

### Example: Dynamic Class Names
```javascript
const isActive = true;
const buttonClass = `btn ${isActive ? "btn-primary" : "btn-secondary"}`;

console.log(buttonClass); // btn btn-primary
```

### Example: JSX with Dynamic Text
```javascript
const name = "Alice";

const App = () => {
  return <h1>{`Welcome, ${name}!`}</h1>;
};

export default App;
```

---

###  Summary
✔ Use **backticks (`)** instead of quotes for strings.  
✔ Embed variables and expressions with `${}`.  
✔ Perfect for **React dynamic content** and **conditional classes**.

---
