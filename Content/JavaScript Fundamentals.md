## **1\. What is JavaScript?**

- **Definition**: JavaScript (JS) is a programming language used to make websites **interactive**.
- **Role in Web Development**:
    - **Frontend**: Runs in the browser (e.g., animations, form validation).
    - **Backend**: With Node.js, it can power servers and databases (covered later!).
- **Key Features**:
    - Dynamic typing (no need to declare variable types).
    - Event-driven (responds to clicks, inputs, etc.).
    - Supports both procedural and object-oriented programming.

---
## **2\. Setting Up Your Environment**

### **Tools You Need**
1.  **Browser**: Chrome/Firefox (for running JS and using DevTools).
2.  **Code Editor**: [VS Code](https://code.visualstudio.com/) (recommended).
3.  **Node.js**: Install from [nodejs.org](http://nodejs.org) (to run JS outside the browser).

### **Quick Test**
Open your browser’s console (**Ctrl+Shift+J** on Chrome) and type:

```javascript
console.log("Hello, JavaScript!");
```

If you see the message printed, you’re ready!

---
## **3\. Basic Syntax & Concepts**

### **Variables**
Store data using `let`, `const`, or `var`:

```javascript
let age = 20;       // Can be reassigned
const PI = 3.14;    // Cannot be reassigned
var oldVariable;    // Avoid (legacy, has scope issues)
```

### **Data Types**

| **Type**    | **Example**          | **Description**                 |
| ----------- | -------------------- | ------------------------------- |
| `number`    | `42`, `3.14`         | Integers or decimals.           |
| `string`    | `"Hello"`, `'World'` | Text in quotes.                 |
| `boolean`   | `true`, `false`      | Logical values.                 |
| `object`    | `{ name: "Alice" }`  | Collections of key-value pairs. |
| `array`     | `[1, 2, 3]`          | Ordered lists.                  |
| `undefined` | `let x;`             | Declared but not assigned.      |
### **Operators**

```javascript
// Arithmetic
let sum = 5 + 3;    // 8
let isEven = (sum % 2 === 0); // true

// Comparison
10 > 5;   // true
"5" == 5; // true (loose equality)
"5" === 5; // false (strict equality)

// Logical
true && false; // false (AND)
true || false; // true (OR)
!true;         // false (NOT)
```

### **Functions**
Define reusable blocks of code:

```javascript
// Function Declaration
function greet(name) {
  return `Hello, ${name}!`;
}

// Function Expression (Arrow Syntax)
const add = (a, b) => a + b;
```

### **Control Flow**
**Conditionals**:

```javascript
let temperature = 25;

if (temperature > 30) {
  console.log("It's hot!");
} else if (temperature > 20) {
  console.log("It's warm."); // This will run
} else {
  console.log("It's cool.");
}
```

**Loops**:

```javascript
// For Loop
for (let i = 0; i < 5; i++) {
  console.log(i); // Prints 0-4
}

// While Loop
let count = 3;
while (count > 0) {
  console.log(count); // 3, 2, 1
  count--;
}
```

---
## **4\. DOM Manipulation Basics**

The **Document Object Model (DOM)** represents your webpage as a tree of objects. Use JS to modify it!
### **Select Elements**

```javascript
// By ID
const header = document.getElementById("header");

// By CSS Selector
const button = document.querySelector(".btn");
```
### **Modify Content**

```javascript
header.textContent = "New Heading";  // Change text
button.style.backgroundColor = "blue"; // Change style
```
### **Event Listeners**
Make elements interactive:

```javascript
button.addEventListener("click", () => {
  console.log("Button clicked!");
});
```

---
## **5\. Live Session Recap**

**What We Covered**:
1.  Wrote "Hello, World!" in the console.
2.  Created variables and practiced arithmetic.
3.  Built a function to calculate the area of a circle.
4.  Used `if/else` to decide if a number is even/odd.
5.  Built a simple click counter with DOM manipulation.

**Code from Live Demo**:

```html
<!DOCTYPE html>
<html>
<body>
  <h1 id="counterLabel">0</h1>
  <button id="incrementBtn">Click Me!</button>
  <script>
    let count = 0;
    const label = document.getElementById("counterLabel");
    const button = document.getElementById("incrementBtn");

    button.addEventListener("click", () => {
      count++;
      label.textContent = count;
    });
  </script>
</body>
</html>
```

---
## **6\. Practice Exercises**

6.  **FizzBuzz**: Print numbers 1-100. For multiples of 3, print "Fizz"; for multiples of 5, print "Buzz"; for both, print "FizzBuzz".
7.  **Temperature Converter**: Write a function that converts Celsius to Fahrenheit.
8.  **Interactive List**: Create a webpage where users can add/remove list items using a text input and buttons.

---
## **7\. Common Pitfalls & Tips**
- **Pitfalls**:
	- Forgetting `let`/`const` when declaring variables (causes global scope pollution).
	- Using `"=="` instead of `"==="` (strict equality is safer).
	- - Missing curly braces `{}` in loops/conditionals.
- **Tips**:
	- Use `console.log()` to debug.
	- Format code consistently (e.g., indentation).
	- Practice with small projects (e.g., calculators, quizzes).

---
## **8\. Additional Resources**

- **MDN JavaScript Guide**: [Link](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- **FreeCodeCamp JS Course**: [Link](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/)
- [**JavaScript.info**](http://JavaScript.info): [Link](https://javascript.info/)

---
### **Cheat Sheet**

```javascript
// Variables
let name = "Alice";
const age = 25;

// Functions
const multiply = (a, b) => a * b;

// Arrays
let fruits = ["apple", "banana"];
fruits.push("orange"); // Add item

// Objects
const user = {
  name: "Bob",
  age: 30
};
```