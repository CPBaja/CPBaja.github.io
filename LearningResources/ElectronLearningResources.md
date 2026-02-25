# ⚛️ Electron Tutorials

Welcome to the Electron learning guide! This document explains how we package our web applications into standalone desktop software and provides the resources to help you understand desktop architecture.

## What is Electron Used For?

On our team, **Electron is used to turn our Angular web applications into cross-platform desktop apps.** While web browsers are great, they have strict security limitations (they can't easily read or write local files) and usually require an internet connection. By wrapping apps like **DataVis** in Electron, we can run them natively on Windows, macOS, or Linux laptops down in the pit lane or out in the desert where we don't have internet access. It also allows our applications to read local telemetry log files directly from the car's SD cards or USB connections.

Under the hood, Electron combines the **Chromium rendering engine** (the frontend UI) with a **Node.js environment** (the backend file-system access) into a single executable.



---

## Prerequisites

Before diving into Electron, make sure you understand the foundational web technologies:
1. **Node.js:** Installed and working.
2. **Web Basics:** You should have a solid grasp of HTML, CSS, JavaScript, and ideally Angular, as Electron simply acts as the wrapper for these technologies.

---

## 📚 Learning Resources

Electron introduces a specific mental model: you are essentially writing a Node.js server and a web browser at the exact same time. Choose the track below that fits your experience level.

### 1. The Absolute Basics (For Beginners)
Start by understanding what Electron is and how a basic app is structured before throwing Angular into the mix.
* **[Electron Quick Start Guide](https://www.electronjs.org/docs/latest/tutorial/quick-start)**: The official documentation is excellent. This guide will walk you through creating a simple window and loading a web page into it.

### 2. Main vs. Renderer Processes (Core Concept)
This is the most important concept in Electron. If you do not understand this, your apps will not work.
* **[Process Model](https://www.electronjs.org/docs/latest/tutorial/process-model)**: Read this to understand the difference between the **Main Process** (which manages the app lifecycle and has full computer access) and the **Renderer Process** (which simply displays the Angular UI).
* **[Inter-Process Communication (IPC)](https://www.electronjs.org/docs/latest/tutorial/ipc)**: Learn how to pass messages between the UI and the backend. For example, if the user clicks "Save File" in the Angular UI, it must send an IPC message to the Main process to actually write the file to the hard drive.

### 3. Integrating with Angular
Once you understand Electron's architecture, look into how we merge it with our frontend framework.
* **[ngx-electronyzer](https://github.com/mkloubert/ngx-electronyzer) or similar boilerplates:** While the specific library we use may update over time, review community patterns on how Angular's build output (the `dist/` folder) is passed into the Electron `BrowserWindow` to be rendered.

---

## 🛑 Team Best Practices for Electron

When building or updating our desktop applications, strictly adhere to these rules:

* **Security First (Context Isolation):** Never enable `nodeIntegration: true` in your Renderer process. Doing so gives the frontend UI direct access to the computer's operating system, which is a massive security risk. Always use `contextBridge` and a `preload.js` script to safely expose specific Node.js functions to Angular.
* **Keep the Main Process Light:** The Main process handles the operating system level tasks. If you run heavy mathematical calculations (like processing massive DataVis telemetry arrays) on the Main thread, you will freeze the entire application. Offload heavy processing to Web Workers.
* **Use `path.join()`:** When referencing file paths (like loading an icon or a local JSON file), never hardcode strings like `'./assets/icon.png'`. When Electron packages the app into an `.exe`, the folder structure changes. Always use Node's `path.join(__dirname, 'assets/icon.png')` to ensure paths resolve correctly in production.