# 🟩 Node.js Tutorials

Welcome to the Node.js learning guide! This document explains the runtime environment that powers our entire web development ecosystem and provides resources to help you master it.

## What is Node.js Used For?

Historically, JavaScript could only run inside a web browser to make websites interactive. **Node.js changed that.** It is a runtime environment that allows us to execute JavaScript and TypeScript directly on our computers, just like C++ or Python.

On our team, Node.js is the invisible backbone of almost everything we do in software:
* **Tooling:** It runs the Angular CLI, allowing us to compile and serve **PartSync** and **DataVis** locally.
* **Desktop Apps:** It provides the backend file-system access for our **Electron** applications.
* **Package Management:** It gives us `npm` (Node Package Manager), which we use to download external libraries (like charting tools or database drivers) into our projects.



---

## Prerequisites

Before writing Node scripts, you must have the environment set up:
1.  **Node.js & npm:** Installed via a version manager like `nvm` (as detailed in our [Node.js Setup Guide](../SetUpGuides/SetUpNodeJS.md)).
2.  **JavaScript Knowledge:** You must understand standard JavaScript (especially asynchronous concepts like Promises and async/await) before diving into Node.

---

## 📚 Learning Resources

Node.js is vast, but for frontend and desktop developers, understanding package management and the core modules is the most critical step. Choose the track below that fits your experience level.

### 1. The Absolute Basics (For Beginners)
Start by understanding what Node actually is and how to run a basic script from your terminal.
* **[Node.js Official: Introduction to Node.js](https://nodejs.org/en/learn/getting-started/introduction-to-nodejs)**: Read this brief overview to understand the philosophy behind Node and how it differs from browser-based JavaScript.
* **[Running Node Scripts](https://nodejs.org/en/learn/getting-started/how-to-run-nodejs-scripts-from-the-command-line)**: Learn how to execute a `.js` file directly from your VSCode terminal using the `node` command.

### 2. NPM and Package Management (Core Concept)
Every Node project revolves around the `package.json` file. You must understand how this works to manage your project's dependencies.
* **[NPM Crash Course (Traversy Media)](https://www.youtube.com/watch?v=jHDhaSSKmB0)**: A great visual breakdown of how `npm init`, `npm install`, and the `node_modules` folder work.
* **[Understanding package.json](https://nodejs.org/en/learn/getting-started/the-package-json-guide)**: Learn the difference between `dependencies` (libraries your app needs to run) and `devDependencies` (tools you only need while writing code, like testing frameworks).

### 3. Core Modules (For Intermediate Developers)
Node comes with built-in modules that allow you to interact with the operating system. You will use these heavily if you are working on our Electron apps or writing build scripts.
* **[The File System (`fs`) Module](https://nodejs.org/en/learn/manipulating-files/reading-files-with-nodejs)**: Learn how to read, write, and delete files on the hard drive.
* **[The Path (`path`) Module](https://nodejs.org/en/learn/manipulating-files/nodejs-file-paths)**: Learn how to safely construct file paths that work on both Windows and macOS.

---

## 🛑 Team Best Practices for Node.js

When working within our Node ecosystems, adhere to these rules:

* **Never Commit `node_modules`:** This folder can easily grow to gigabytes in size. It must *always* be included in your `.gitignore` file. We only commit the `package.json` and `package-lock.json` files, which allow other team members to generate their own `node_modules` folder by running `npm install`.
* **Use NVM (Node Version Manager):** Always ensure you are running the specific version of Node dictated by the project's documentation or `.nvmrc` file to avoid "it works on my machine" compatibility errors.
* **Prefer ES Modules (`import`):** Historically, Node used CommonJS (`require()`) to load modules. Modern Node supports standard ES Modules (`import` / `export`). We prefer ES Modules to keep our syntax perfectly aligned with our Angular TypeScript code.
* **Don't Block the Event Loop:** Node is single-threaded. If you write a massive, synchronous `while` loop, you will freeze the entire server or application. Always use asynchronous methods (like `fs.readFile` instead of `fs.readFileSync`) for heavy operations.