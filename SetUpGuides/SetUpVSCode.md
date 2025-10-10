# Set Up Visual Studio Code (VSCode)

This guide covers installing VSCode, configuring essential settings for a consistent development experience, installing necessary extensions, and setting up local environments.

## 1. Installation

1.  **Download and Install:**
    - Go to the official VSCode download page: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
    - Download and install the version for your operating system.
2.  **Open the Application:**
    - Launch **Visual Studio Code**.

---

## 2. Recommended Settings

These settings ensure automatic formatting, consistent file endings, and improved terminal history.

1.  **Open the Command Palette:**
    - Press **`Ctrl+Shift+P`** (Windows/Linux) or **`Cmd+Shift+P`** (Mac).
2.  **Open Settings JSON:**
    - Type `user settings json` and select **`Preferences: Open User Settings (JSON)`**.
3.  **Apply Settings:**
    - **Copy and paste** the following configuration block into the file, ensuring you replace the existing content or merge it correctly within the `{}` braces.

```json
{
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "files.autoSave": "onFocusChange",
  "files.insertFinalNewline": true,
  "files.trimFinalNewlines": true,
  "files.trimTrailingWhitespace": true,
  "terminal.integrated.scrollback": 1000000,
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "black-formatter.args": ["--line-length", "160"]
}
```

# 3. Extensions

These extensions provide language support, formatting, and essential tools for the team's projects.

1.  **Open Extensions View:**
    - Press **`Ctrl+Shift+X`** (Windows/Linux) or **`Cmd+Shift+X`** (Mac).
2.  **Install Extensions:**
    - Search for each extension **Name** in the marketplace and click **Install**.

| Name                     | Author     | Software or Firmware |
| ------------------------ | ---------- | -------------------- |
| Angular Language Service | Angular    | Software             |
| Black Formatter          | Microsoft  | Both                 |
| C/C++                    | Microsoft  | Both                 |
| ESLint                   | Microsoft  | Software             |
| Hex Editor               | Microsoft  | Both                 |
| Live Share               | Microsoft  | Both                 |
| PlatformIO IDE           | PlatformIO | Firmware             |
| Prettier                 | Prettier   | Software             |
| Python                   | Microsoft  | Both                 |

# 4. Python/C++ Setup (Optional)

This step is only necessary if you are running **Python** or **C++** code _directly on your computer_ (not just for firmware compilation). You need to configure the language interpreter or compiler path for VSCode to work correctly with local projects.

1.  **Open the Command Palette:**
    - Press **`Ctrl+Shift+P`** (Windows/Linux) or **`Cmd+Shift+P`** (Mac).
2.  **Open Walkthrough:**
    - Type `walkthrough` and select **`Welcome: Open Walkthrough...`**.
3.  **Configure Environment:**
    - **For Python:** Click **`Get Started with Python Development`** and follow the guided instructions to select your local interpreter.
    - **For C++:** Click **`Get Started with C++ Development`** and follow the guided instructions to set up your local compiler (e.g., GCC or Clang).
