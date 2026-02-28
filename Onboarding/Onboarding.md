# 🚀 Software Team Onboarding Guide

Welcome to the team! This guide will walk you step-by-step through setting up your workspace, learning our workflows, and getting your local development environment ready.

> **Important:** To ensure a smooth setup process, please follow each phase in order. We will use **PartSync** as our working example throughout this guide, as it is a great starting point for new members to get their hands dirty.

---

## Step 1: Getting Connected 💬

Before installing any software, let's get you into our communication hub. Slack is where all team discussions, subsystem updates, and quick questions happen.

### 1. Join the Workspace
* **Accept Invite:** Check your email for the team Slack invitation.
* **Profile Setup:** Create your account and set up your profile. *(Please use a clear photo of your face so teammates can easily recognize you!)*

### 2. Join the Required Channels
Use the channel browser to search for and join the following:
* `#ss-software`
* `#ss-electrons`
* `#car-partsync`

### 3. Slack Communication Guidelines

* 🔔 **Enable All Notifications:** To ensure you don't miss important team discussions or urgent updates, please configure Slack to notify you for everything. Click your profile picture, select **Preferences** > **Notifications**, and choose **"All new messages"**.
* 🧵 **Keep it in the thread:** Always use the "Reply in Thread" feature when responding to a specific message, rather than sending a new message to the entire channel. This is crucial for keeping our channels organized, readable, and easy to search.
* 📢 **Announcements:** The `#a-announcements` channel is reserved strictly for management updates.

---

## Step 2: Requesting Tool Access 🔐

Now that you are in Slack, you need to request permissions for our development tools.

Head over to the `#ss-software` channel:
1.  Check the tabs at the top for **Software Links**.
2.  Fill out the access request form to get permissions for:
* **GitHub** (Codebase & Issue Tracking)
* **Supabase** (Database)
* **PartSync** (Application Access)

> **🔑 Secret Management:** In the `Software Links` section, you will also find a secure method for accessing our environment secrets for PartSync. Please take note of where this link is; you will need it later during the local setup.

---

## Step 3: Learning the Ropes & Leveling Up 📚

*While you wait for a team lead to approve your access requests from Step 2, use this time to learn how we operate and familiarize yourself with our tech stack.*

### 1. Core Development Practices
To maintain a clean and reliable codebase, all team members follow these standards:
* **Issue Tracking:** Keep all discussion and context related to an issue within the GitHub issue comments.
* **Pull Requests (PRs):** Always open a PR. Never push code directly to `main` or other shared branches.
* **Project Board Maintenance:** Keep the GitHub Project Board updated as the status of your assigned issues changes.
* **Standardization:** Follow our team guidelines for commit messages and PR titles.
* **Rebasing:** We maintain a linear history. **We exclusively use rebasing—no merge commits.**

### 2. Required Reading
These documents form the foundation of how our software team operates. Please read through all of them before writing any code:
* 📖 [Best Practices](../BestPractices/BestPractices.md)
* 📖 [Commit Standards](../BestPractices/CommitStandards.md)
* 📖 [Rebasing Guide](../BestPractices/RebasingGuide.md)
* 📖 [Opening a Pull Request](../BestPractices/OpeningAPullRequest.md)
* 📖 [Starting an Issue](../BestPractices/StartingAnIssue.md)

### 3. Dive Into the Tech Stack
New to Angular? Never used Docker? Want to brush up on TypeScript? We’ve curated a set of learning resources specifically tailored to how we build software for the car. **We highly encourage you to explore these guides now** so you’re ready to hit the ground running once your access is approved.

👉 **[Learning Resources](../LearningResources/LearningResourcesIndex.md)**

---

## Step 4: Verifying Access & Local Setup ⚙️

Once a lead confirms your access has been granted, verify everything is working and set up your local machine.

### 1. Verify GitHub Access
Navigate to our team's GitHub organization and open the **PartSync** repository. Confirm you can:
* View the repository code and the "Issues" tab.
* View the Project Board (**Projects → PartSync**) and move issues between columns.

### 2. Verify Supabase Access
Log into Supabase and confirm you can see and access the **PartSync** project dashboard.

*(If you are missing any of the above permissions, drop a note in `#ss-software`.)*

### 3. Development Setup
Now it's time to configure your local machine. Head over to our comprehensive setup directory and complete the guides:

👉 **[Setup Guides Directory](../SetUpGuides/SetUpGuides.md)**

> **Note for software onboarding:** If you are following this software onboarding guide, you do **not** need to complete the Altium setup guide unless you are also doing electrical PCB design work.

Before continuing, verify that the following tools are installed and running without errors:
* **Node.js**
* **Angular CLI**
* **Docker**
* **Supabase CLI**

---

## Step 5: Your First Development Task 🎯

Once your environment is fully set up, we ask that all new members complete two interactive tutorials. These run directly in your browser and ensure you are comfortable with the modern Angular workflow we use:

1.  **[Learn Angular Tutorial](https://angular.dev/tutorials/learn-angular)** *(Core fundamentals)*
2.  **[Angular Signals Guide](https://angular.dev/tutorials/signals)** *(State management)*

Once you've completed these, you're ready to pick up your first real issue for PartSync. Welcome aboard!
