
# React In-Depth: PropTypes

**PropTypes** is a type-checking feature in React that helps ensure components receive the correct props.  
It is especially useful for debugging and maintaining large applications.

---

## **1. What is PropTypes?**
- PropTypes allow you to **validate the type of props** passed to a component.
- Helps **catch bugs** by ensuring props have the expected type.

---

## **2. Installing PropTypes**
PropTypes is a separate library in modern React.
```bash
npm install prop-types
```

---

## **3. Using PropTypes in a Component**
Example:
```javascript
import React from "react";
import PropTypes from "prop-types";

const Greeting = ({ name, age }) => {
  return (
    <h1>Hello, {name}. You are {age} years old.</h1>
  );
};

Greeting.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number
};

export default Greeting;
```

**Explanation:**
- `name` must be a **string** and is **required**.
- `age` must be a **number** (optional).

---

## **4. Common PropTypes Types**
| Type          | Description                  |
|---------------|------------------------------|
| `PropTypes.string` | String value            |
| `PropTypes.number` | Number value            |
| `PropTypes.bool`   | Boolean value           |
| `PropTypes.array`  | Array value             |
| `PropTypes.object` | Object value            |
| `PropTypes.func`   | Function                |
| `PropTypes.node`   | Anything renderable     |
| `PropTypes.element`| React element           |

---

## **5. Default Props**
You can provide default values using `defaultProps`.

Example:
```javascript
Greeting.defaultProps = {
  age: 18
};
```

If `age` is not passed, it defaults to `18`.

---

##  **Why Use PropTypes?**
✔ Improves **code reliability**.  
✔ Helps **catch errors early** during development.  
✔ Acts as **documentation for your component’s expected props**.

---

###  Summary
✔ PropTypes validate **data types** for props.  
✔ Use `isRequired` for mandatory props.  
✔ Set **defaultProps** for optional props.

---
