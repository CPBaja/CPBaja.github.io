# 🌐 HTML Tutorials

Welcome to the HTML learning guide! This document explains how we write structural code for our web applications and provides the best resources to get you up to speed.

## What is HTML Used For?

On our team, **HTML is used to structure our frontend web applications**, such as PartSync and DataVis. It acts as the skeleton of our user interfaces, defining where text, buttons, forms, and images live on the screen.

Because we use **Angular** as our frontend framework, we rarely write standard, static HTML files. Instead, we write **Angular Templates**. These are HTML files highly supercharged with Angular-specific syntax that allows them to communicate directly with our TypeScript code, dynamically updating the screen as data changes.



---

## Prerequisites

Before writing HTML for our web apps, make sure your editor is ready:
1. **VSCode:** Installed and configured.
2. **Angular Language Service Extension:** Install this via the VSCode marketplace. It provides crucial autocompletion, error checking, and navigation inside your HTML template files.

---

## 📚 Learning Resources

Whether you have never written a line of HTML or just need to learn how it integrates with Angular, choose the track below that fits your experience level.

### 1. The Absolute Basics (For Beginners)
If you are completely new to web development, you need to understand standard HTML elements, tags, and attributes before mixing in Angular.
* **[MDN Web Docs: Introduction to HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)**: MDN is the industry standard for web documentation. Read through this to understand how elements wrap content to structure a page.
* **[W3Schools HTML Tutorial](https://www.w3schools.com/html/)**: A great interactive resource if you want to test HTML tags in your browser and see the immediate output.

### 2. Angular Templates (For Intermediate Developers)
Once you know basic HTML, you need to learn how Angular extends it. This is how we make our applications dynamic.
* **[Angular.dev: Template Syntax](https://angular.dev/guide/templates)**: Read this official guide to understand the core Angular template features:
    * **Interpolation (`{{ value }}`):** Displaying variables from your TypeScript code.
    * **Property Binding (`[property]="value"`):** Passing data into HTML attributes.
    * **Event Binding (`(click)="doSomething()"`):** Triggering TypeScript functions from HTML button clicks or inputs.

### 3. Modern Angular Control Flow
We use modern Angular standards. Instead of older structural directives like `*ngIf` and `*ngFor`, we use Angular's built-in control flow block syntax.
* **[Angular.dev: Control Flow](https://angular.dev/guide/templates/control-flow)**: Learn how to use `@if`, `@else`, and `@for` directly inside your HTML files to conditionally show elements or render lists of data (like a list of parts in PartSync).

---

## 🛑 Team Best Practices for HTML

When writing templates for our team projects, keep these rules in mind:
* **Write Semantic HTML:** Use the correct tags for the job. Use `<button>` for clickable actions, `<nav>` for navigation, and `<main>` for primary content. Do not just use `<div>` for everything; semantic HTML is crucial for accessibility and clean code.
* **Keep Logic Out of the Template:** Your HTML should only dictate *what* is displayed, not *how* it is calculated. Do not put complex math or logical conditions directly in your HTML interpolation. Calculate that in your TypeScript component and bind the resulting variable to the HTML.
* **Use Component Scoping:** Keep your HTML files small and focused. If a file is getting too long (e.g., over 150 lines), it probably needs to be broken down into smaller, reusable Angular child components.