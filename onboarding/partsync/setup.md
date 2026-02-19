# 🛠️ PartSync Development Setup

This guide walks you through setting up the PartSync development environment from scratch. Follow each section in order.

---

## Prerequisites

Complete the following general setup guides before continuing:

1. **[Set Up GitHub Desktop](../../SetUpGuides/SetUpGitHubDesktop.md)** — Install and configure GitHub Desktop.
2. **[Set Up VSCode](../../SetUpGuides/SetUpVSCode.md)** — Install and configure Visual Studio Code.
3. **[Set Up Node.js](../../SetUpGuides/SetUpNodeJS.md)** — Install Node.js and npm.

You will also need **Python 3** installed. Download it from [https://www.python.org/downloads/](https://www.python.org/downloads/).

---

## 1. Clone the Repository

1. Open **GitHub Desktop**.
2. Go to **File > Clone Repository**.
3. Select the **CPBaja** organization tab.
4. Choose **Parts-Management** from the list.
5. Set your local path (e.g., `Documents/GitHub/Parts-Management`).
6. Click **Clone**.

Or using the terminal:

```bash
git clone https://github.com/CPBaja/Parts-Management.git
cd Parts-Management
```

---

## 2. Set Up the Frontend

All commands in this section run from the `frontend/` directory.

```bash
cd frontend
npm install
```

This installs all JavaScript dependencies listed in `package.json`.

### Start the Development Server

```bash
npm start
```

The app will open at [http://localhost:3000](http://localhost:3000). The page reloads automatically when you save changes.

---

## 3. Set Up the Backend

All commands in this section run from the `backend/` directory.

### Create a Python Virtual Environment

```bash
cd backend
python3 -m venv venv
```

### Activate the Virtual Environment

**macOS / Linux:**

```bash
source venv/bin/activate
```

**Windows:**

```bash
venv\Scripts\activate
```

### Install Python Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Configure Environment Variables

The backend requires a `.env` file in the `backend/` directory containing the database connection string.

```
MONGODB_URL=<connection-string>
```

> **Do not commit the `.env` file.** It contains credentials and is excluded from version control via `.gitignore`.

To obtain the `.env` file, contact a team maintainer or ask in the team chat.

### Verify the Database Connection

After adding the `.env` file, run the included test to confirm the connection works:

```bash
python3 tests/test_db_url.py
```

A successful connection will print a confirmation message with no errors.

---

## 5. Verify Your Setup

With both the frontend and backend configured:

1. Start the backend server. The specific run command is documented in the [backend README](https://github.com/CPBaja/Parts-Management/tree/main/backend).
2. In a separate terminal, start the frontend:

   ```bash
   cd frontend
   npm start
   ```

3. Open [http://localhost:3000](http://localhost:3000) in your browser.
4. If you see the PartSync parts list UI, your setup is complete.

---

## 🔧 Troubleshooting

### Node Version Mismatch

If `npm install` or `npm start` fails with compatibility errors, check your Node.js version:

```bash
node -v
```

Use the **LTS version** of Node.js. Download it from [https://nodejs.org/](https://nodejs.org/). Reinstall if necessary.

### Missing `.env` File

If the backend throws a connection error on startup, the `.env` file is likely missing or incorrectly placed. Confirm:

- The file is named exactly `.env` (not `.env.txt`).
- It is located in the `backend/` directory.
- It contains the `MONGODB_URL` variable.

### Python `venv` Not Activating

If `source venv/bin/activate` fails, ensure Python 3 is installed and that the `venv` module is available:

```bash
python3 -m venv --help
```

On some systems you may need to install it separately:

```bash
# Ubuntu/Debian
sudo apt install python3-venv
```

### MongoDB Connection Refused

If `test_db_url.py` fails:

- Confirm your `.env` file has the correct `MONGODB_URL`.
- Confirm you have network access (MongoDB Atlas requires internet).
- Contact a maintainer — the cluster IP allowlist may need to be updated.

### Frontend Compiles but Shows No Data

If the UI loads but the parts list is empty:

- Confirm the backend server is running.
- Check the browser console for network errors.
- Ensure the frontend is making requests to the correct backend address.

---

← Back to [PartSync Overview](index.md) | [Onboarding Index](../index.md)
