# ⚡ Supabase Tutorials

Welcome to the Supabase learning guide! This document explains how we manage our backend database, user authentication, and APIs without having to write a custom server from scratch.

## What is Supabase Used For?

On our team, **Supabase is our complete backend solution** for web applications like **PartSync**. Instead of writing and hosting our own custom Node.js/Express server to talk to a database, Supabase provides it all out of the box.

Under the hood, Supabase is just a powerful **PostgreSQL database**. However, it wraps that database with a suite of open-source tools that automatically generate secure REST APIs, handle user logins (Authentication), and even provide real-time web sockets (so if someone updates a part quantity in the shop, your screen updates instantly).



We interact with Supabase in two ways:
1. **The Supabase Dashboard:** A web interface to view our data and manage tables.
2. **The Supabase JS Client:** A library we install in our Angular apps to fetch and update data using TypeScript.

---

## Prerequisites

Before interacting with our databases, ensure you have the proper access and tools:
1. **Supabase Access:** You must have been invited to the team's Supabase organization (see the [Onboarding Guide](../Onboarding/Onboarding.md)).
2. **Supabase CLI & Docker:** Installed and configured. We use the CLI alongside Docker to run a local copy of the database on your machine so you don't accidentally break production data while testing.

---

## 📚 Learning Resources

Supabase is very developer-friendly, but you still need a foundational understanding of relational databases. Choose the track below that fits your experience level.

### 1. The Absolute Basics (Database Fundamentals)
If you have never worked with a database before, you need to understand tables, columns, rows, and relationships (like how a `Part` relates to a `Category`).
* **[Supabase Crash Course (Traversy Media)](https://www.youtube.com/watch?v=7uKQBl9uZ00)**: A fantastic, visual introduction to setting up a project, creating tables, and querying data.
* **[PostgreSQL Tutorial](https://www.postgresqltutorial.com/)**: While Supabase provides a UI, knowing basic SQL (Structured Query Language) is incredibly helpful for complex data tasks.

### 2. The Supabase JavaScript Client (For Intermediate Developers)
Learn how to actually connect our Angular apps to the database.
* **[Supabase JS/TS Documentation](https://supabase.com/docs/reference/javascript/introduction)**: Read the official docs on how to initialize the client, and how to use the `select()`, `insert()`, `update()`, and `delete()` methods.
* **[Authentication in Supabase](https://supabase.com/docs/guides/auth)**: Understand how users log in and how Supabase manages session tokens.

### 3. Local Development & Migrations (Advanced)
We do not make changes directly to the production database by clicking around the dashboard. We use code.
* **[Local Development with Supabase CLI](https://supabase.com/docs/guides/cli/local-development)**: Learn how to use `supabase start` to spin up your local Docker environment.
* **[Database Migrations](https://supabase.com/docs/guides/cli/local-development#database-migrations)**: Learn how to write SQL migration files. When you want to add a new column to the `Parts` table, you write a migration file, test it locally, and then that file is applied to production during deployment.

---

## 🛑 Team Best Practices for Supabase

When working with our backend, strictly adhere to these security and workflow rules:

* **Always Enable RLS (Row Level Security):** By default, a new table in Supabase is completely public—anyone on the internet with your API key can delete all your data. **You must enable RLS on every table** and write policies that dictate exactly who can read or write data (e.g., "Only authenticated team members can insert new parts").
* **Never Push to Production Directly:** Do not use the Supabase web dashboard to alter the schema of the production database. All schema changes (new tables, new columns, altered data types) must be done locally via CLI migrations, committed to Git, and reviewed in a Pull Request.
* **Generate TypeScript Types:** We use Supabase's CLI to automatically generate TypeScript `interfaces` directly from our database schema. Whenever you change the database, regenerate these types (`supabase gen types typescript`) so your Angular code instantly knows about the new columns and maintains strict type safety.
* **Never Expose the Service Role Key:** Supabase provides two keys: an `anon` (public) key and a `service_role` key. The `service_role` key bypasses all security rules. **Never** put the `service_role` key in your Angular frontend code. It is only for secure backend scripts.