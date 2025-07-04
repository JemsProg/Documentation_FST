# JavaScript Crash Course: Arrays & `map()`

## 🧠 What You'll Learn

- What is an Array?
- How to loop over arrays using `.map()`
- Why `.map()` is useful (especially in React)

---

## 📦 What is an Array?

An **array** is a list-like object used to store multiple values in a single variable.

```js
const skills = ["JavaScript", "React", "HTML", "CSS"];
```

Each item inside the array is called an **element**, and they are accessed by their index (starting from 0).

```js
console.log(skills[0]); // Output: JavaScript
```

---

## 🔁 Looping with `.map()`

`.map()` is a built-in array method used to **loop through** an array and **transform** each element.

### Syntax:

```js
array.map(callbackFunction);
```

The callback function runs once for **each item** in the array.

### Example:

```js
const skills = ["JS", "React"];

skills.map((skill) => console.log(skill));
// Output:
// JS
// React
```

### Example with return:

```js
const upperSkills = skills.map((skill) => skill.toUpperCase());
console.log(upperSkills); // Output: ["JS", "REACT"]
```

---

## 🧑‍💻 Why `.map()` is Important in React

In React, `.map()` is used a lot when rendering **lists of elements**.

Example:

```js
const skills = ["JS", "React"];

return (
  <ul>
    {skills.map((skill, index) => (
      <li key={index}>{skill}</li>
    ))}
  </ul>
);
```

- `key={index}` helps React keep track of elements.
- `{skill}` outputs the text inside `<li>`.

---

## 🧪 Quick Practice:

1. Create an array of your favorite foods.
2. Use `.map()` to print each food with `console.log()`.

```js
const foods = ["Pizza", "Burger", "Pasta"];
foods.map((food) => console.log(food));
```

✅ You're now ready to use arrays and `.map()` like a pro!
