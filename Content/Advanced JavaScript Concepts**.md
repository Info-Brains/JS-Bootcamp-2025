### **ES6+ Features**
- **Arrow Functions**: Shorter syntax and lexical `this` binding.
    ```javascript
    const multiply = (a, b) => a * b;
    ```
- **Classes**: Syntactic sugar for prototype-based inheritance.
    ```javascript
    class Rectangle {
      constructor(height, width) {
        this.height = height;
        this.width = width;
      }
    }
    ```
- **Destructuring**: Extract values from arrays/objects easily.
    ```javascript
    const [x, y] = [10, 20];
    const { name, age } = user;
    ```

### **Asynchronous Programming**
- **Promises**: Handle asynchronous operations cleanly.
    ```javascript
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .catch(error => console.error(error));
    ```
- **Async/Await**: Write asynchronous code synchronously.
    ```javascript
    async function loadData() {
      const data = await fetchData();
      console.log(data);
    }
    ```

### **Closures**
Functions retain access to their outer scope even after execution.
```javascript
function createCounter() {
  let count = 0;
  return () => count++; // Closure retains access to `count`
}
const counter = createCounter();
counter(); // 0, 1, 2...
```

---
## Example: Build Conway’s Game of Life**

### **What is the Game of Life?**
A cellular automaton with simple rules:
1. **Survival**: Live cells with 2-3 neighbors stay alive.
2. **Death**: Live cells with <2 or >3 neighbors die.
3. **Birth**: Dead cells with exactly 3 neighbors become alive.

---

### **Step 1: HTML Setup**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Game of Life</title>
  <style>
    canvas { border: 1px solid #333; }
    .controls { margin: 10px; }
  </style>
</head>
<body>
  <div class="controls">
    <button id="startBtn">Start</button>
    <button id="clearBtn">Clear</button>
    <button id="randomBtn">Random</button>
  </div>
  <canvas id="gridCanvas"></canvas>
  <script src="game.js"></script>
</body>
</html>
```

---

### **Step 2: JavaScript Implementation (game.js)**

#### **Game Class (State Management)**
```javascript
class Game {
  constructor(rows, cols, cellSize) {
    this.rows = rows;
    this.cols = cols;
    this.cellSize = cellSize;
    this.grid = this.createEmptyGrid();
    this.isRunning = false;
  }

  createEmptyGrid() {
    return Array(this.rows).fill()
      .map(() => Array(this.cols).fill(false));
  }

  randomize() {
    this.grid = this.grid.map(row => 
      row.map(() => Math.random() > 0.85)
    );
  }

  countNeighbors(x, y) {
    let count = 0;
    for (let dy = -1; dy <= 1; dy++) {
      for (let dx = -1; dx <= 1; dx++) {
        if (dx === 0 && dy === 0) continue; // Skip self
        const nx = (x + dx + this.cols) % this.cols; // Wrap edges
        const ny = (y + dy + this.rows) % this.rows;
        if (this.grid[ny][nx]) count++;
      }
    }
    return count;
  }

  update() {
    const newGrid = this.createEmptyGrid();
    for (let y = 0; y < this.rows; y++) {
      for (let x = 0; x < this.cols; x++) {
        const neighbors = this.countNeighbors(x, y);
        const isAlive = this.grid[y][x];
        newGrid[y][x] = (isAlive && (neighbors === 2 || neighbors === 3)) ||
                        (!isAlive && neighbors === 3);
      }
    }
    this.grid = newGrid;
  }
}
```

---

#### **Renderer Class (Canvas Drawing)**
```javascript
class Renderer {
  constructor(canvas, game) {
    this.canvas = canvas;
    this.ctx = canvas.getContext('2d');
    this.game = game;
    canvas.width = game.cols * game.cellSize;
    canvas.height = game.rows * game.cellSize;
  }

  draw() {
    this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);
    for (let y = 0; y < this.game.rows; y++) {
      for (let x = 0; x < this.game.cols; x++) {
        if (this.game.grid[y][x]) {
          this.ctx.fillStyle = '#000';
          this.ctx.fillRect(
            x * this.game.cellSize,
            y * this.game.cellSize,
            this.game.cellSize - 1,
            this.game.cellSize - 1
          );
        }
      }
    }
  }
}
```

---

#### **Event Listeners & Game Loop**
```javascript
document.addEventListener('DOMContentLoaded', () => {
  const game = new Game(40, 40, 15);
  const canvas = document.getElementById('gridCanvas');
  const renderer = new Renderer(canvas, game);
  let intervalId = null;

  // Button Event Handlers
  document.getElementById('startBtn').addEventListener('click', () => {
    game.isRunning = !game.isRunning;
    if (game.isRunning) {
      intervalId = setInterval(() => {
        game.update();
        renderer.draw();
      }, 100);
    } else {
      clearInterval(intervalId);
    }
  });

  document.getElementById('clearBtn').addEventListener('click', () => {
    game.grid = game.createEmptyGrid();
    renderer.draw();
  });

  document.getElementById('randomBtn').addEventListener('click', () => {
    game.randomize();
    renderer.draw();
  });

  // Initial Draw
  renderer.draw();
});
```

---

### **How to Run**
1. Save the HTML and JS files.
2. Open the HTML file in a browser.
3. Click **Random** to seed the grid, then **Start** to begin the simulation.
4. Click **Clear** to reset or **Stop** to pause.

**Try It!** Experiment with different grid sizes and update speeds by modifying the `Game` constructor parameters.
```