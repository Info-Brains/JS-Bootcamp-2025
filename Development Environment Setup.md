## **1. Install Node.js and npm**

**Why?** Node.js allows you to run JavaScript outside the browser, and npm (Node Package Manager) helps manage dependencies.

• Download and install **Node.js** from [nodejs.org](https://nodejs.org/) (choose the **LTS version**)
• Verify installation:

```
node -v
npm -v
```

---
## **2. Install a Code Editor**

Use **Visual Studio Code (VS Code)** for writing and running JavaScript.
- Download from [code.visualstudio.com](https://code.visualstudio.com/)
- Install useful extensions:
- **Live Server** (for running web pages easily)

---
## **3. Install Git**

**Why?** Git helps track changes in your code and collaborate with others.
- Download and install **Git** from [git-scm.com](https://git-scm.com/)
- Check if Git is installed:

```
git --version
```

- Set up your name and email (required for commits):

```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---
## **4. Create a JavaScript Project**

**Create a New Folder**

```
mkdir js-bootcamp
cd js-bootcamp
```

**Initialize a New Project**

```
npm init -y
```

This creates a package.json file to manage project dependencies.

---
## **5. Run a Simple Web Server (for frontend projects)**

If you’re working with HTML, CSS, and JavaScript:
- Install **Live Server** extension in VS Code
- Open an index.html file
- Click **“Go Live”** in the bottom-right of VS Code

OR use this command in the terminal:

```
npx serve .
```

---
## **7. Useful Commands**

```
# Check Node.js and npm versions
node -v
npm -v

# Create a folder and navigate into it
mkdir my-project
cd my-project

# Initialize npm
npm init -y

# Install a package
npm install package-name

# Start a simple web server
npx serve .

# Check Git status
git status

# Commit changes
git add .
git commit -m "First commit"
```

---
## **8. Conclusion**
You’re now ready to start coding in JavaScript! 🎉
