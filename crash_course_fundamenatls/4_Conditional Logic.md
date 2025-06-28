# JavaScript Crash Course: Conditional Logic

## 🔍 What You'll Learn

- How to use `if`, `else`, and `else if`
- What is a **ternary operator**
- How to make decisions in your code

---

## ⚖️ Conditional Statements

Conditional statements let your program make **decisions** based on values or conditions.

---

## ✅ `if`, `else if`, `else`

```js
const age = 18;

if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}
```

You can add `else if` for more conditions:

```js
const score = 85;

if (score >= 90) {
  console.log("A grade");
} else if (score >= 80) {
  console.log("B grade");
} else {
  console.log("Needs improvement");
}
```

---

## ❓ Ternary Operator

The **ternary operator** is a **shorter way** to write an `if-else` statement.

### Syntax:

```js
condition ? valueIfTrue : valueIfFalse;
```

### Example:

```js
const loggedIn = true;
const message = loggedIn ? "Welcome" : "Login first";
console.log(message); // Output: Welcome
```

Another example:

```js
const age = 16;
const canVote = age >= 18 ? "Yes" : "No";
console.log(canVote); // Output: No
```

---

## 🎓 Beginner Tips

- Use `if-else` when you need **more control** or multiple branches.
- Use ternary when you want to **return or assign** a value quickly.
- Avoid **nesting too many ternaries**; it can get hard to read.

---

## 🔮 Quick Practice:

1. Create a variable `isMember = true`.
2. Use ternary to print "Access Granted" or "Access Denied".

```js
const isMember = true;
const access = isMember ? "Access Granted" : "Access Denied";
console.log(access);
```

---

You've now mastered conditional logic and can control your app's behavior!

