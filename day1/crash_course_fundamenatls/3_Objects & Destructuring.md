# JavaScript Crash Course: Objects & Destructuring

## 📁 What You'll Learn

- What is an object in JavaScript?
- How to access object properties
- How to use destructuring to write cleaner code

---

## 🔑 What is an Object?

An **object** is a collection of **key-value pairs**. Each key is like a variable name, and each value holds data.

```js
const user = {
  name: "Jems",
  age: 22,
  isStudent: true,
};
```

### Accessing Object Properties

You can access values using **dot notation**:

```js
console.log(user.name); // Output: Jems
console.log(user.age); // Output: 22
```

Or using **bracket notation**:

```js
console.log(user["name"]); // Output: Jems
```

---

## 🌍 Destructuring

**Destructuring** is a shortcut that lets you extract values from an object into variables quickly.

### Example:

```js
const user = { name: "Jems", age: 22 };

const { name } = user;

console.log(name); // Output: Jems
```

You can also extract multiple values:

```js
const { name, age } = user;
console.log(name); // Output: Jems
console.log(age); // Output: 22
```

### Rename while destructuring:

```js
const { name: fullName } = user;
console.log(fullName); // Output: Jems
```

---

## 🤯 Why Use Destructuring?

- Makes code **cleaner** and **shorter**
- Avoids repeating `object.property` multiple times
- Common in **React props** and **API responses**

---

## 🔮 Quick Practice:

1. Create an object `book` with `title`, `author`, and `year`
2. Destructure the values and `console.log()` them

```js
const book = {
  title: "JavaScript Basics",
  author: "Jane Doe",
  year: 2025,
};

const { title, author } = book;
console.log(title); // JavaScript Basics
console.log(author); // Jane Doe
```

---

You're now ready to use objects and destructuring like a pro!
