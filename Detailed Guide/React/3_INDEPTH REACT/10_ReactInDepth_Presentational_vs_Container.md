
#  React In-Depth: Presentational vs Container Components

Before **React Hooks** were introduced, developers often separated components into two categories:  
**Presentational Components** (UI only) and **Container Components** (logic and state).  
This pattern is still useful for understanding **separation of concerns**.

---

## **1. What is a Presentational Component?**
- **Focus:** How things look (UI).
- **Characteristics:**
  - Receives **data via props**.
  - Usually a **functional component**.
  - Does NOT handle state or side effects.

###  Example: Presentational Component
```javascript
const UserCard = ({ name, age }) => {
  return (
    <div>
      <h2>{name}</h2>
      <p>Age: {age}</p>
    </div>
  );
};

export default UserCard;
```

**Explanation:**  
- Displays user info based on props.  
- No state or API calls.

---

## **2. What is a Container Component?**
- **Focus:** How things work (logic, data fetching, state).
- **Characteristics:**
  - Handles **state and side effects** (like API calls).
  - Passes data down to presentational components via **props**.

###  Example: Container Component
```javascript
import React, { useState, useEffect } from "react";
import UserCard from "./UserCard";

const UserContainer = () => {
  const [user, setUser] = useState({ name: "", age: 0 });

  useEffect(() => {
    // Simulate API call
    setTimeout(() => {
      setUser({ name: "Alice", age: 25 });
    }, 1000);
  }, []);

  return <UserCard name={user.name} age={user.age} />;
};

export default UserContainer;
```

**Explanation:**  
- Fetches user data and stores it in state.  
- Passes `name` and `age` to `UserCard` (presentational).  

---

## **3. Why This Pattern Was Popular**
✔ Helps separate **UI from business logic**.  
✔ Makes components **easier to test and reuse**.  
✔ Used heavily before **Hooks** made state management in functional components easy.

---

## **4. Do We Still Use It Today?**
- This pattern is less common because **Hooks** allow logic to be shared without splitting components.
- But it's still useful when building **large apps** or using **Redux/Context** for state.

---

##  **Modern Alternative**
- Instead of strict Presentational/Container split, we use:
  ✔ **Custom Hooks** for logic.  
  ✔ **Functional Components** for UI.  

Example:
```javascript
const useUser = () => {
  const [user, setUser] = useState({ name: "", age: 0 });
  useEffect(() => {
    setTimeout(() => {
      setUser({ name: "Alice", age: 25 });
    }, 1000);
  }, []);
  return user;
};

const UserCard = ({ name, age }) => <h2>{name} ({age})</h2>;

const App = () => {
  const user = useUser();
  return <UserCard name={user.name} age={user.age} />;
};
```

---

###  Summary
✔ **Presentational Component** → UI only, no state.  
✔ **Container Component** → Handles logic and data fetching.  
✔ Modern React uses **Hooks** and **Context** instead of this strict pattern.

---
