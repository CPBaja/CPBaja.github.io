# 🏗️ PartSync Architecture

This page describes the high-level architecture of PartSync, grounded in the repository's README and source structure.

---

## High-Level System Overview

PartSync is a **two-tier web application** with a React frontend and a Python Flask backend. The frontend communicates with the backend over HTTP, and the backend reads and writes part data to a hosted MongoDB Atlas database.

```
┌────────────────────────────────┐
│         Browser (User)         │
│   React App — localhost:3000   │
└────────────┬───────────────────┘
             │ HTTP requests
┌────────────▼───────────────────┐
│    Flask Backend (Python)      │
│    Handles API routes          │
└────────────┬───────────────────┘
             │ PyMongo
┌────────────▼───────────────────┐
│    MongoDB Atlas (Cloud DB)    │
│    cpbajabomdev cluster        │
└────────────────────────────────┘
```

> The diagram above is a conceptual representation. Refer to the source code for specific route and data model details.

---

## Frontend Architecture

The frontend is a **React** application bootstrapped with [Create React App](https://create-react-app.dev/).

### Key Characteristics

- Written in **JavaScript**
- Styled with **Bootstrap** components
- Linted with **ESLint** and formatted with **Prettier**
- Runs on `localhost:3000` in development

### Available Frontend Commands

Run these from the `frontend/` directory:

```bash
npm start        # Start the development server
npm test         # Run the test suite
npm run build    # Build for production
npm run lint     # Lint with ESLint
npm run lint:fix # Auto-fix lint errors
npm run format   # Format with Prettier
```

---

## Backend Architecture

The backend is a **Python Flask** application connected to a cloud-hosted MongoDB database.

### Key Characteristics

- Written in **Python**
- Uses **Flask** as the web framework
- Connects to **MongoDB Atlas** via **PyMongo**
- Requires a `.env` file containing the `MONGODB_URL` environment variable
- Linted with **PyCodeStyle** and **PyLint**

### Database

The database is hosted on **MongoDB Atlas** in the `cpbajabomdev` cluster. Access requires credentials stored in the `.env` file — contact a team maintainer to obtain this file.

---

## Data Flow

A typical read request flows as follows:

1. The user interacts with the React frontend (e.g., filters by subsystem).
2. The frontend sends an HTTP GET request to the Flask backend.
3. The Flask backend queries MongoDB using PyMongo.
4. MongoDB returns the matching documents.
5. Flask serializes the response and returns JSON to the frontend.
6. React renders the updated part list.

---

## Repository Structure

```
Parts-Management/
├── frontend/           # React application
│   ├── src/            # Application source code
│   ├── public/         # Static assets
│   └── package.json    # npm dependencies and scripts
├── backend/            # Flask application
│   ├── tests/          # Backend test suite
│   ├── requirements.txt# Python dependencies
│   └── .env            # Environment variables (not committed)
└── README.md
```

> For the full file tree, clone the repository and explore it locally.

---

← Back to [PartSync Overview](index.md) | [Onboarding Index](../index.md)
