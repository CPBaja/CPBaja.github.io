# 🅰️ Angular Tutorials

Welcome to the Angular learning guide! This document explains the core framework that powers our web frontend and provides the best resources to help you build interactive, scalable applications.

## What is Angular Used For?

On our team, **Angular is our frontend web framework**. We use it to build Single-Page Applications (SPAs) like **PartSync** and **DataVis**.

Instead of writing separate, massive HTML and JavaScript files, Angular allows us to build applications using **Components**. A component is a self-contained block of code that encapsulates its own HTML (structure), SCSS (style), and TypeScript (logic). You can think of components like custom HTML tags that we build ourselves (e.g., `<app-part-list>`) and piece together to create the full application interface.



Angular also provides built-in tools for routing (navigating between pages without reloading the browser), handling forms, and managing data from our Supabase backend.

---

## Prerequisites

Before diving into Angular, you must have your local environment set up and a basic understanding of web languages:
1. **Node.js & Angular CLI:** Installed and working. *(Run `ng version` in your terminal to check).*
2. **Web Basics:** You should have read through the HTML, CSS/SCSS, and JS/TS guides in this wiki. Angular relies heavily on TypeScript.

---

## 📚 Learning Resources

Angular is a massive framework, but you do not need to know everything to start contributing. Focus on the tracks below in order.

### 1. The Interactive Basics (For Beginners)
If you are completely new to Angular, start with the official interactive tutorials. They run directly in your browser, so you don't even need to spin up a local environment.
* **[Angular.dev: Learn Angular](https://angular.dev/tutorials/learn-angular)**: This is required reading. It will walk you through creating your first components, using control flow (`@if`, `@for`), and binding data.

### 2. Core Concepts (For Intermediate Developers)
Once you finish the basic tutorial, you need to understand how we structure real-world apps. Read these specific guides from the official documentation:
* **[Components](https://angular.dev/guide/components)**: Understand the lifecycle of a component (like `ngOnInit`) and how to pass data between parent and child components using `input()` and `output()`.
* **[Services and Dependency Injection](https://angular.dev/guide/di)**: Components should only handle UI logic. If you need to fetch data from Supabase, you write that code in a **Service**, and "inject" that service into your component.
* **[Routing](https://angular.dev/guide/routing)**: Learn how to configure the Angular Router so users can navigate between pages (e.g., going from `/dashboard` to `/inventory`).

### 3. Modern State Management (Signals)
We use modern Angular standards, which means we use **Signals** to manage our application state (data that changes over time, like a part's inventory count).



* **[Angular.dev: Signals Tutorial](https://angular.dev/tutorials/signals)**: Learn how to use `signal()`, `computed()`, and `effect()` to make your UI react instantly when underlying data changes, without the complexity of older RxJS streams.

---

## 🛑 Team Best Practices for Angular

When writing Angular code for team projects, adhere to these rules:
* **Standalone Components:** We use modern Standalone components. Do not use `NgModules` unless you are maintaining legacy code.
* **Smart vs. Dumb Components:** * *Dumb (Presentational) Components:* Only display data and emit events (e.g., a button or a table). They should not inject services.
    * *Smart (Container) Components:* Inject services, fetch data from the database, and pass that data down to the dumb components.
* **Keep Constructors Clean:** Use the `constructor()` only for injecting dependencies. Put initialization logic (like fetching initial data) inside the `ngOnInit()` lifecycle hook.
* **Unsubscribe:** If you *do* have to use RxJS Observables instead of Signals, make sure you unsubscribe from them when the component is destroyed (`ngOnDestroy`) to prevent memory leaks.