
#  Modern JavaScript for React: Rest and Spread Operators

The **rest** (`...`) and **spread** (`...`) operators use the same three-dot syntax but serve different purposes. They are widely used in React for handling **props**, **state updates**, and **passing data**.

---

## **1. Spread Operator (Expanding Arrays/Objects)**
The **spread operator** is used to **expand elements** of an array or object into individual elements.

###  Example: Spreading Arrays
```javascript
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4, 5];
console.log(newNumbers); // [1, 2, 3, 4, 5]
```

###  Example: Spreading Objects
```javascript
const user = { name: "Alice", age: 25 };
const updatedUser = { ...user, city: "Manila" };
console.log(updatedUser); // { name: "Alice", age: 25, city: "Manila" }
```

**Where Used in React:**  
- When **updating state** without mutating the original object.
```javascript
const [user, setUser] = useState({ name: "Alice", age: 25 });

const updateAge = () => {
  setUser({ ...user, age: 26 }); // ✅ Create new object using spread
};
```

---

## **2. Rest Operator (Collecting Multiple Arguments)**
The **rest operator** is used to **collect multiple arguments** into a single array or object.

###  Example: Rest in Functions
```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4)); // 10
```

###  Example: Rest in Object Destructuring
```javascript
const user = { name: "Alice", age: 25, city: "Manila" };
const { name, ...otherDetails } = user;
console.log(name); // Alice
console.log(otherDetails); // { age: 25, city: "Manila" }
```

**Where Used in React:**  
- When passing **props** to components without explicitly listing them all.
```javascript
const Card = ({ title, ...props }) => {
  return <div>{title} - {props.description}</div>;
};
<Card title="Hello" description="Welcome to React" />;
```

---

##  **Key Difference**
- **Spread** → Expands elements (e.g., combine arrays, copy objects).
- **Rest** → Collects multiple elements into one array/object.

---

###  Summary
✔ **Spread** → Used for copying and merging arrays/objects.  
✔ **Rest** → Used for gathering multiple arguments into one.  
✔ Both are essential for **React props**, **state updates**, and **function arguments**.

---
