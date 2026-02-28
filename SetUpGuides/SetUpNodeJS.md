# Set Up Node.js (via Version Manager)

> **Audience:** Software Only

This guide covers installing Node.js and npm (Node Package Manager) on your local machine using a version manager. We highly recommend this approach as it allows you to easily switch between Node versions for different projects and completely prevents global permission errors.

## 1. Pre-installation: Remove Existing Node.js

If you already have Node.js installed directly from the official website or another package manager, you **must** uninstall it first to prevent conflicting paths and environment variables.

### **Windows**
1. Go to **Settings > Apps > Installed apps**, search for "Node.js", and uninstall it.
2. Delete any remaining folders in `C:\Program Files\nodejs` or `C:\Users\<YourUser>\AppData\Roaming\npm`.

### **macOS/Linux**
* If installed via **Homebrew**, run: `brew uninstall node`
* If installed via the **official package installer**, run the following command to clean up the directories:
    ```bash
    sudo rm -rf /usr/local/bin/npm /usr/local/share/man/man1/node* /usr/local/lib/dtrace/node.d ~/.npm ~/.node-gyp /opt/local/bin/node /opt/local/include/node /opt/local/lib/node_modules
    ```

---

## 2. Install the Version Manager

The tool you use depends on your operating system.

### **macOS and Linux (nvm)**
We use Node Version Manager (`nvm`).

1.  **Install nvm:** Run the installation script in your terminal:
    ```bash
    curl -o- [https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh](https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh) | bash
    ```
2.  **Reload your terminal:** Restart your terminal or run `source ~/.zshrc` (or `source ~/.bashrc`) to load the new path.
3.  **Verify:** Run `nvm --version`.

### **Windows (nvm-windows)**
The original `nvm` script does not support Windows natively, so we use `nvm-windows`.

1.  **Download the installer:** Go to the [nvm-windows releases page](https://github.com/coreybutler/nvm-windows/releases) and download `nvm-setup.exe` from the latest release.
2.  **Run the installer:** Follow the prompts. *Note: If the installer detects an existing Node.js installation you missed in Step 1, allow it to take over control of the version.*
3.  **Verify:** Open a new PowerShell or Command Prompt window and run `nvm version`.

---

## 3. Install Node.js and npm

We recommend using the **LTS (Long-Term Support)** version of Node.js for maximum stability and compatibility with our projects.

1.  **Install the LTS version:**
    ```bash
    nvm install --lts
    ```
2.  **Set it as the active version:**
    ```bash
    nvm use --lts
    ```
3.  **Set as your default (Recommended):**
    ```bash
    nvm alias default 'lts/*'
    ```
    *(Note for Windows users: `nvm-windows` automatically sets the default when you use `nvm use`, so the alias command is not required).*

---

## 4. Verification

Verify that both Node.js and npm are installed correctly by running these commands:

1.  **Check Node.js Version:**
    ```bash
    node -v
    ```
    *This should output the version number, e.g., `v20.11.1`.*

2.  **Check npm Version:**
    ```bash
    npm -v
    ```
    *This should output the npm version number, e.g., `10.2.4`.*

---

## 5. OS-Specific Configuration

Depending on your operating system, you may need to perform a few additional steps to ensure your environment handles scripts and permissions correctly.

### **Windows Users**
Windows often restricts script execution by default, which can block `npm` and `nvm` commands in PowerShell.

**Enable Script Execution:**
If you see an "UnauthorizedAccess" error, open **PowerShell as Administrator** and run:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
*Type `Y` when prompted to confirm.*

### **macOS Users**
You may need to install build tools for certain native npm packages to compile correctly. *Note: Because you are now using nvm, you will never need to use `sudo` for npm commands!*

**Install Xcode Command Line Tools:**
Open your terminal and run:
```bash
xcode-select --install
```
