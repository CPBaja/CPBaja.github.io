# 🐳 Docker Tutorials

Welcome to the Docker learning guide! This document explains how we use containerization to standardize our development environments and provides the best resources to help you master it.

## What is Docker Used For?

On our team, **Docker is used to ensure our software runs exactly the same way on everyone's computer.** Have you ever heard a developer say, *"Well, it works on my machine!"* when code suddenly breaks for someone else? Docker solves this problem. It allows us to package an application—along with all of its dependencies, libraries, and configuration files—into an isolated, standardized unit called a **Container**.



For projects like PartSync, we rely heavily on Docker to run our local database. When you want to test database changes locally, you don't need to manually install PostgreSQL, set up users, or configure network ports. Instead, you simply run a Docker command, and it spins up an exact replica of our production Supabase environment right on your laptop.

---

## Prerequisites

Before diving into Docker, you must have the engine installed and running on your local machine:
1. **Docker Desktop:** Installed and running in the background.
2. *(Windows Users Only):* Ensure you have **WSL 2 (Windows Subsystem for Linux)** installed and enabled, as Docker Desktop for Windows relies on it for optimal performance.

---

## 📚 Learning Resources

Docker operates heavily via the command line. Choose the track below that fits your experience level to understand the core concepts.

### 1. The Absolute Basics (For Beginners)
If you have never used Docker, you need to understand the difference between an **Image** (the blueprint) and a **Container** (the running instance).
* **[Docker's Official Getting Started Guide](https://docs.docker.com/get-started/)**: This is the best place to start. It walks you through pulling your first image, running a container, and understanding basic terminal commands like `docker ps` and `docker stop`.

### 2. Docker Compose (For Intermediate Developers)
While `docker run` is great for a single container, modern web applications (like our Supabase backend) require multiple containers talking to each other (e.g., a database container, an API container, and an authentication container).
* **[Docker Compose Overview](https://docs.docker.com/compose/)**: Learn how we use a single `docker-compose.yml` file to define a multi-container environment. You will use the command `docker-compose up` constantly to start the local backend for PartSync.

### 3. Volumes and Networking
By default, when a Docker container is deleted, all data inside it is lost.
* **[Docker Volumes](https://docs.docker.com/storage/volumes/)**: Learn how to use Volumes to persist database data between container restarts so you don't lose your local PartSync test parts every time you turn off your computer.

---

## 🛑 Team Best Practices for Docker

When working with Docker in our repositories, strictly adhere to these rules:
* **Never Commit Secrets:** Never hardcode passwords, API keys, or database credentials directly into a `Dockerfile` or `docker-compose.yml` file. Always use environment variables passed via a `.env` file (which is ignored by Git).
* **Use `.dockerignore`:** Just like `.gitignore`, always ensure node_modules and local build files are excluded from being copied into your Docker images to keep them small and fast.
* **Clean Up After Yourself:** Docker images and stopped containers can take up massive amounts of hard drive space over time. If your computer is running low on storage, run `docker system prune` in your terminal to safely clear out unused, dangling containers and images.