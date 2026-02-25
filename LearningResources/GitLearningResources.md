# 🌿 Git & GitHub Tutorials

Welcome to the Git learning guide! This document explains our version control system and provides the resources you need to collaborate on our codebase without accidentally deleting your teammates' work.

## What are Git and GitHub Used For?

On our team, **Git is the tool we use to track changes to our code, and GitHub is where we store it.** Imagine working on a massive Google Doc with 10 other people, but instead of text, it's thousands of lines of complex logic for the car. If someone makes a mistake, the whole system crashes. Git solves this by acting as a time machine. It allows you to create a "branch" (a parallel universe of the code), experiment safely, and then carefully merge your changes back into the `main` codebase once they are tested and approved.



While Git is the underlying software that runs on your local computer, **GitHub** is the cloud platform that hosts our Git repositories (like PartSync and DataVis), tracks our issues, and manages our Pull Requests (PRs).

---

## Prerequisites

Before pulling down any team code, ensure your environment is set up:
1. **Git:** Installed on your local machine.
2. **GitHub Account:** You must be added to the team's GitHub organization (see the [Onboarding Guide](../Onboarding/Onboarding.md)).
3. **GitHub Desktop (Optional but Recommended):** A visual interface for Git that makes reviewing your changes before committing much easier. ([See our setup guide](../SetUpGuides/SetUpGitHubDesktop.md)).

---

## 📚 Learning Resources

Git can be notoriously confusing from the command line. Choose the track below that fits your experience level to master our workflow.

### 1. The Absolute Basics (For Beginners)
If you have never used version control, you need to understand the lifecycle of a file: Modified, Staged, and Committed.
* **[GitHub Skills: Introduction to GitHub](https://skills.github.com/)**: This interactive, free course from GitHub is the best starting point. It covers cloning a repository, making a commit, and opening a Pull Request.
* **[Git Handbook (GitHub Docs)](https://guides.github.com/introduction/git-handbook/)**: Read this to understand the fundamental difference between your working directory, the staging area, and your local repository.

### 2. The Team Workflow: Rebasing (Crucial Concept)
As mentioned in our Onboarding Guide, **we do not use standard merge commits.** We use rebasing to keep our project history perfectly linear and readable. You must understand this before opening your first PR.
* **[Atlassian Git Tutorial: Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)**: Read this to understand how `git rebase` works. When you rebase, you are essentially picking up your entire branch and moving it to the tip of the `main` branch.
* **[Team Rebasing Guide](../BestPractices/RebasingGuide.md)**: Once you understand the concept, read our internal guide on exactly how to execute a rebase locally before updating your PR.

### 3. Handling Merge Conflicts (For Intermediate Developers)
Eventually, you and a teammate will edit the exact same line of code at the same time. This causes a merge conflict.
* **[Resolving Merge Conflicts in VSCode](https://code.visualstudio.com/docs/editor/versioncontrol#_merge-conflicts)**: Learn how to use VSCode's built-in conflict resolution tool to safely choose which code to keep (Accept Current Change vs. Accept Incoming Change).

---

## 🛑 Team Best Practices for Git

When contributing to our repositories, strictly adhere to these rules:

* **Never Commit to `main`:** The `main` branch is locked. You must create a new branch for every issue you work on (e.g., `feature/add-login-button` or `bugfix/datavis-crash`) and submit a Pull Request.
* **Write Descriptive Commit Messages:** A commit message like "fixed stuff" is useless. Follow our [Commit Standards](../BestPractices/CommitStandards.md). Use the imperative mood, like "Fix authentication routing bug" or "Add SCSS variables for primary colors".
* **Commit Often, Push Often:** Do not work locally for a week and then drop one massive commit with 5,000 lines of code changes. Break your work into small, logical commits. This makes it infinitely easier for the team to review your PR.
* **Pull Before You Push:** Before you rebase or open a PR, always make sure you have pulled the latest changes from the remote `main` branch into your local machine to ensure your code is up to date with everyone else's work.