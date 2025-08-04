# React In-Depth: Props

**Props (short for Properties)** are a way to pass **data from a parent component to a child component** in React.  
Props make components **dynamic and reusable**.

---

## **1. What are Props?**

- Props are **read-only**.
- Passed from **parent to child** as attributes.
- Cannot be modified by the child component.

Example:

```javascript
const Greeting = ({ name }) => <h1>Hello, {name}!</h1>;

const App = () => <Greeting name="Alice" />;
```

**Output:**

```
Hello, Alice!
```

---

## **2. Why Use Props?**

✔ To **customize components**.  
✔ To make components **reusable**.  
✔ To **share data** between components.

---

## **3. Passing Multiple Props**

Example:

```javascript
const Profile = ({ name, age }) => (
  <p>
    {name} is {age} years old.
  </p>
);

const App = () => <Profile name="Bob" age={25} />;
```

**Output:**

```
Bob is 25 years old.
```

---

## **4. Default Props**

You can set **default values** for props.

Example:

```javascript
const Button = ({ label = "Click Me" }) => <button>{label}</button>;

const App = () => (
  <>
    <Button /> {/* Default label */}
    <Button label="Submit" />
  </>
);
```

**Output:**

```
Click Me
Submit
```

---

## **5. Props Are Read-Only**

❌ You cannot modify props inside the child component.

Bad Example:

```javascript
const Greeting = ({ name }) => {
  name = "Changed"; // ❌ Error
  return <h1>{name}</h1>;
};
```

Props should only be **read and displayed**.

---

## **Props vs State**

| Feature      | Props             | State                |
| ------------ | ----------------- | -------------------- |
| **Source**   | Parent component  | Inside the component |
| **Mutable?** | ❌ No (read-only) | ✅ Yes               |
| **Purpose**  | Pass data         | Manage local data    |

---

### Summary

✔ Props = **Data passed from parent to child**.  
✔ Props are **read-only**.  
✔ Use props to make components **reusable and dynamic**.

---
