# 🔩 PartSync — Project Overview

**PartSync** is the parts management web application for the Cal Poly Baja SAE team. It gives team members a central place to track every part on the car — from procurement status to CAD availability.

---

## What Is PartSync?

PartSync is an internal web application that allows team members to **add, edit, and monitor** the parts they need to purchase or manufacture for the Baja car. It stores structured data about each part including its subsystem, subassembly, status, priority, stock level, and CAD link.

The software is currently in alpha and is not yet publicly released.

### Core Problem It Solves

Without a centralized system, parts tracking happens in spreadsheets or informal channels. PartSync replaces that with a consistent, searchable interface that gives every subsystem lead visibility into part status across the entire build.

---

## How PartSync Fits Into Baja Software

The Baja Software Subsystem builds and maintains internal tooling that supports the rest of the team. PartSync is the primary tool for the build/manufacturing workflow. It connects electrical, mechanical, and logistics work by giving everyone a shared view of part status.

Other software projects (Telemetry, MobileScout, etc.) follow the same development patterns established here.

---

## Tech Stack

PartSync uses a split frontend/backend architecture:

| Layer | Technology |
|-------|------------|
| Frontend | React (Create React App), JavaScript |
| Backend | Python, Flask |
| Database | MongoDB Atlas (via PyMongo) |
| Linting | ESLint + Prettier (frontend), PyCodeStyle + PyLint (backend) |

> All stack details are sourced directly from the [PartSync repository README](https://github.com/CPBaja/Parts-Management).

---

## Tracked Subsystems

PartSync currently tracks parts across the following vehicle subsystems:

- Chassis
- Powertrain
- Front Suspension
- Rear Suspension
- Steering
- Brakes
- Ergonomics
- Composites
- Electronics

---

## Expected Member Commitment

Contributing to PartSync requires:

- Attending the onboarding meeting
- Completing the development environment setup
- Participating in sprint planning and standups
- Reviewing pull requests from teammates
- Completing at least one issue per sprint

---

## 📂 PartSync Documentation

| Page | Description |
|------|-------------|
| **[Architecture](architecture.md)** | System design and repo structure |
| **[Setup Guide](setup.md)** | Local development environment setup |
| **[Contribution Workflow](workflow.md)** | Branching, PRs, labels, and code standards |
| **[First Contribution](first-task.md)** | Step-by-step guide for your first PR |

---

← Back to [Onboarding Index](../index.md)
