
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
## **1\. Practice Exercises**

1.  **FizzBuzz**: Print numbers 1-100. For multiples of 3, print "Fizz"; for multiples of 5, print "Buzz"; for both, print "FizzBuzz".
2.  **Temperature Converter**: Write a function that converts Celsius to Fahrenheit.
3.  **Interactive List**: Create a webpage where users can add/remove list items using a text input and buttons.

---
## **2\. Common Pitfalls & Tips**
- **Pitfalls**:
	- Forgetting `let`/`const` when declaring variables (causes global scope pollution).
	- Using `"=="` instead of `"==="` (strict equality is safer).
	- - Missing curly braces `{}` in loops/conditionals.
- **Tips**:
	- Use `console.log()` to debug.
	- Format code consistently (e.g., indentation).
	- Practice with small projects (e.g., calculators, quizzes).

---
## **3\. Additional Resources**

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