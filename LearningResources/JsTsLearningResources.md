# 📜 JavaScript & TypeScript Tutorials

Welcome to the JavaScript and TypeScript learning guide! This document explains the core logic languages driving our web applications and provides the best resources to help you write clean, bug-free code.

## What are JS and TS Used For?

On our team, **JavaScript (JS) and TypeScript (TS) are the brains of our web applications**, such as PartSync and DataVis. If HTML is the skeleton and CSS is the skin, JS/TS is the nervous system—it handles fetching data from our Supabase database, calculating metrics, and making the user interface interactive.

While web browsers only understand JavaScript, **we write all of our Angular applications in TypeScript**.



TypeScript is a "superset" of JavaScript. It takes standard JS and adds **static typing** (similar to what you see in C++). This means you have to explicitly define what type of data a variable holds (e.g., a `string`, a `number`, or a custom `Part` object). The Angular CLI then compiles (transpiles) your TypeScript into standard JavaScript before it runs in the browser. We use TS because it catches errors in VSCode *before* you ever run the code, saving hours of debugging.

---

## Prerequisites

Before writing TS for our web apps, ensure your environment is ready:
1. **Node.js:** Installed on your machine.
2. **VSCode:** Installed and configured.
3. *(Note: VSCode has built-in TypeScript support, so you do not need to install extra language extensions for it to work.)*

---

## 📚 Learning Resources

If you are coming from C++, JavaScript's asynchronous nature can feel a bit strange. Choose the track below that fits your experience level.

### 1. The Absolute Basics (Vanilla JavaScript)
Even though we write TypeScript, you must understand underlying JavaScript concepts first.
* **[MDN Web Docs: JavaScript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)**: Start here to understand variables, functions, and events.
* **[JavaScript.info: The Modern JavaScript Tutorial](https://javascript.info/)**: A fantastic, comprehensive guide. Focus specifically on **Objects**, **Arrays**, and **Promises/async-await**.

### 2. Understanding Asynchronous Code
Web apps spend a lot of time waiting (e.g., waiting for a user to click a button, or waiting for Supabase to return a list of parts).

* **[MDN Web Docs: Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)**: You must understand how the Event Loop, Promises, and `async`/`await` work so your code doesn't freeze the application while waiting for data.

### 3. TypeScript Features (For Intermediate Developers)
Once you know JS, learn how to add type safety.
* **[TypeScript Handbook: The Basics](https://www.typescriptlang.org/docs/handbook/2/basic-types.html)**: Read the official handbook to understand how to define Types and Interfaces. This is how we define the shape of our database tables in our frontend code.

---

## 🛑 Team Best Practices for TS/JS

When writing logic for team projects, strictly adhere to these rules:
* **Never use `any`:** The `any` type completely disables TypeScript's safety checks. If you don't know the type of a variable, figure it out and define an `interface` for it. Code PRs containing `any` will be rejected.
* **Use `const` and `let` (Never `var`):** Always use `const` for variables that won't be reassigned. Use `let` if the value will change. Never use `var`, as its scoping rules cause unpredictable bugs.
* **Use Arrow Functions:** Prefer `() => {}` syntax over the `function` keyword, especially for callbacks, as it preserves the context of `this` within your Angular components.
* **Leverage Angular Signals:** For reactive state management (like updating the UI when a part quantity changes), use Angular Signals rather than older RxJS BehaviorSubjects whenever possible.