# Modern JavaScript for React: Classes

Classes in JavaScript provide a **blueprint for creating objects** with properties and methods.  
They are used in React for **Class Components** (older approach) and still useful for understanding **object-oriented programming**.

---

## **1. What Are Classes?**

- Introduced in **ES6**.
- A class is a **template for creating objects**.
- Uses the `class` keyword.

---

### Example: Basic Class

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(
      `Hello, my name is ${this.name} and I am ${this.age} years old.`
    );
  }
}

const user = new Person("Alice", 25);
user.greet(); // Hello, my name is Alice and I am 25 years old.
```

---

## **2. Class Inheritance**

Classes can **inherit properties and methods** from another class using `extends`.

```javascript
class Animal {
  constructor(type) {
    this.type = type;
  }
  sound() {
    console.log("Some sound...");
  }
}

class Dog extends Animal {
  constructor(name) {
    super("Dog");
    this.name = name;
  }
  sound() {
    console.log(`${this.name} barks!`);
  }
}

const dog = new Dog("Buddy");
dog.sound(); // Buddy barks!
```

---

## **Classes in React**

Before React Hooks, **Class Components** were used to manage state and lifecycle.

### Example of a Class Component:

```javascript
import React, { Component } from "react";

class App extends Component {
  render() {
    return <h1>Hello from a Class Component!</h1>;
  }
}

export default App;
```

---

## **When to Use Classes in React?**

- Mostly in **older projects** (React now prefers functional components with hooks).
- Still useful to understand **component lifecycle methods** (like `componentDidMount`).

---

### Summary

✔ Classes define **blueprints for objects**.  
✔ Use `constructor` for initializing values.  
✔ Use `extends` and `super()` for inheritance.  
✔ React **now prefers functional components**, but classes are still important for legacy code.

---
