
#  Control Flow and Conditionals (JavaScript ES6)

Control flow allows you to make decisions in your program by executing different code based on conditions. This is key for adding logic to your applications.

---

## **1. Conditional Statements (`if`, `else if`, `else`)**
Conditional statements allow your program to perform different actions based on whether conditions are true or false.

###  Syntax:
```javascript
if (condition) {
  // Code runs if condition is true
} else if (anotherCondition) {
  // Code runs if anotherCondition is true
} else {
  // Code runs if none of the conditions are true
}
```

###  Example:
```javascript
let age = 18;

if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}
```

**Where to Use:**
- Form validation
- Displaying different content for different users
- Applying discounts in e-commerce based on conditions

---

## **2. Comparison Operators**
Used to compare values inside conditions.

| Operator | Meaning                | Example             |
|----------|------------------------|----------------------|
| `==`     | Equal to (loose)      | `5 == "5"` → true   |
| `===`    | Equal (strict)        | `5 === "5"` → false |
| `!=`     | Not equal (loose)     | `5 != "6"` → true   |
| `!==`    | Not equal (strict)    | `5 !== "5"` → true  |
| `<`      | Less than             | `3 < 5` → true      |
| `>`      | Greater than          | `10 > 5` → true     |
| `<=`     | Less than or equal    | `5 <= 5` → true     |
| `>=`     | Greater than or equal | `7 >= 8` → false    |

---

## **3. Logical Operators**
Combine multiple conditions.

| Operator | Description          | Example                                |
|----------|----------------------|----------------------------------------|
| `&&`     | AND (both true)      | `age >= 18 && age < 60`              |
| `||`     | OR (at least one)    | `role === "admin" || role === "user"`|
| `!`      | NOT (negate value)   | `!(age < 18)`                        |

###  Example:
```javascript
let isLoggedIn = true;
let isAdmin = false;

if (isLoggedIn && isAdmin) {
  console.log("Welcome, Admin!");
} else {
  console.log("Access limited.");
}
```

---

## **4. Ternary Operator**
Short form of `if-else` for quick decisions.

###  Syntax:
```javascript
condition ? valueIfTrue : valueIfFalse;
```

###  Example:
```javascript
let age = 20;
let message = age >= 18 ? "Adult" : "Minor";
console.log(message); // Adult
```

**Where to Use:**
- Quick UI decisions
- Setting default values in code

---

###  Best Practices:
- Use `===` and `!==` for strict comparisons.
- Use ternary for simple, one-line decisions.
- For multiple conditions, prefer `if-else` for readability.
