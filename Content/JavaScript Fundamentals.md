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

