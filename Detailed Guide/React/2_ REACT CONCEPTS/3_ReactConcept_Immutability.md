# React Concept: Immutability

**Immutability** means **not changing data directly**.  
Instead of modifying an existing object or array, you create a **new copy with updated values**.

---

## **1. What is Immutability?**

- Data structures should **not be changed in place**.
- React relies on immutability to **detect changes and re-render efficiently**.

---

### Example: Mutable (❌ Bad Practice)

```javascript
const numbers = [1, 2, 3];
numbers.push(4); // Directly modifies the original array
console.log(numbers); // [1, 2, 3, 4]
```

**Why is this bad in React?**

- React uses **shallow comparison** to check if state changed.
- If you mutate state directly, React **might not re-render**.

---

## **2. Immutable (Good Practice)**

Instead of modifying the original, **create a new copy**:

```javascript
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4]; // ✅ Spread operator creates new array
console.log(newNumbers); // [1, 2, 3, 4]
```

---

## **3. Immutability in React State**

React state should **never be updated directly**.

**Bad Example (❌):**

```javascript
const [user, setUser] = useState({ name: "Alice", age: 25 });
user.age = 26; // ❌ Mutating state directly
```

**Good Example (✅):**

```javascript
const [user, setUser] = useState({ name: "Alice", age: 25 });
setUser({ ...user, age: 26 }); // ✅ Creates new object with updated age
```

---

## **Why Immutability is Important in React**

✔ Helps React detect state changes efficiently.  
✔ Avoids unexpected bugs.  
✔ Works well with **functional programming principles**.

---

### Summary

✔ **Never modify state directly**.  
✔ Use **spread operator** or methods that return new arrays/objects (`map`, `filter`).  
✔ Immutability = **New object, not changed old one**.

---
