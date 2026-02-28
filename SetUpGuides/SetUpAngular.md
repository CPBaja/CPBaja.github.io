# Set Up Angular

> **Audience:** Software Only

This guide covers the installation and configuration of the Angular CLI (Command Line Interface). Angular is the primary framework we use for building dynamic, single-page web applications for the team, including tools like DataVis and PartSync.

## 1. Prerequisites

Before installing Angular, you must have the following tools set up on your machine. Please refer to the corresponding guides in our documentation index if you haven't completed these steps:

* **Node.js & npm:** Angular requires an active Long-Term Support (LTS) version of Node.js. ([See: Set up Node.js](SetUpNodeJS.md))
* **VSCode:** Our recommended code editor for Angular development. ([See: Set up VSCode](SetUpVSCode.md))
* **GitHub Desktop / Git:** Necessary for cloning our application repositories. ([See: Set up GitHub Desktop](SetUpGitHubDesktop.md))

*(Note: We highly recommend installing the **Angular Language Service** extension in VSCode for autocompletion, error checking, and navigation within your Angular templates.)*

## 2. Install the Angular CLI

The Angular CLI is a command-line tool that allows you to initialize, develop, scaffold, and maintain Angular applications directly from a command shell.

1.  Open your terminal (macOS/Linux) or Command Prompt/PowerShell (Windows).
2.  Run the following npm command to install the Angular CLI globally on your system:
    ```bash
    npm install -g @angular/cli
    ```
    *If you followed our Node.js setup guide and are using a version manager like `nvm`, this command will execute smoothly without requiring administrative privileges.*

## 3. Verification

Once the installation completes, verify that the Angular CLI is ready to use:

1.  In your terminal, run:
    ```bash
    ng version
    ```
2.  This command will output details about your Angular CLI version, Node.js environment, and operating system.

## 4. Running an Existing Team Project

If you are onboarding and need to run an existing team application on your local machine, follow these steps:

1.  **Clone the Repository:** Use GitHub Desktop or Git via the terminal to clone the project repository to your local workspace.
2.  **Install Dependencies:** Navigate into the project's root directory in your terminal and install the project-specific packages:
    ```bash
    cd path/to/project-folder
    npm install
    ```
3.  **Serve the Application:** Start the local development server:
    ```bash
    ng serve
    ```
4.  Open your web browser and navigate to `http://localhost:4200/`. The application will automatically reload whenever you save changes to the source files in VSCode.

## 5. Angular Workspace Structure



When you open one of our Angular projects in VSCode, you'll see a standard workspace structure. The most important directory for active development is `src/app/`, which contains the components, services, HTML templates, and CSS/SCSS styles that make up the application.
