# 🌱 Your First Contribution to PartSync

This guide walks you through making your first contribution to PartSync from start to finish — no 1:1 help required.

Before you begin, make sure you have:

- ✅ Completed the [Development Setup](setup.md)
- ✅ Read the [Contribution Workflow](workflow.md)

---

## Step 1 — Find a Good First Issue

1. Go to the [Parts-Management Issues page](https://github.com/CPBaja/Parts-Management/issues).
2. Click the **Labels** dropdown and select **`good first issue`**.
3. Browse the open issues and read a few descriptions.
4. Choose an issue that:
   - Is **unassigned**
   - Has **clear requirements**
   - Matches your current skills (frontend JS or backend Python)

---

## Step 2 — Claim the Issue

1. Open the issue you want to work on.
2. In the right-hand sidebar, find **Assignees**.
3. Click **Assign yourself**.

This signals to the team that the issue is taken and prevents duplicate work.

4. If the project uses a board, move the card from **Sprint** to **In Progress**.

---

## Step 3 — Create Your Branch

Always create your branch from the **issue page**, not from your local terminal. This links the branch to the issue automatically.

1. Scroll down to the **Development** section on the issue page.
2. Click **Create a branch**.
3. Use the naming convention:

   ```
   issue-<issue-number>
   ```

   **Example:**

   ```
   issue-42
   ```

4. Click **Create branch**.

---

## Step 4 — Pull the Branch Locally

After creating the branch on GitHub, pull it to your machine:

**Using GitHub Desktop:**
- In GitHub Desktop, click **Fetch origin** then switch to your new branch from the branch dropdown.

**Using the terminal:**

```bash
git fetch
git checkout issue-42
```

---

## Step 5 — Make Your Changes

Work on the changes described in the issue. As you go:

- Run `npm run lint` (frontend) or check PyLint output (backend) frequently.
- Run `npm test` (frontend) to make sure existing tests still pass.
- Commit in small, logical increments.

### Commit Message Format

```
#<issue-number> <imperative description of change>
```

**Example:**

```
#42 Add filter by subassembly to catalog view
```

---

## Step 6 — Open a Pull Request

When your changes are ready:

1. Push your branch to GitHub (GitHub Desktop: click **Push origin**).
2. Navigate to the repository's **Pull Requests** tab.
3. Click **New pull request**.
4. Set your feature branch as the source and `main` as the target.
5. Title the PR:

   ```
   Issue #42 Add filter by subassembly to catalog view
   ```

6. Write a brief description of what you changed and why.
7. Assign a teammate as the **Reviewer**.
8. Click **Create pull request**.

See the full guide: **[Opening a Pull Request](../../BestPractices/OpeningAPullRequest.md)**

---

## Step 7 — Respond to Review Feedback

Your reviewer may leave comments or request changes:

- Address each comment with a code change or a reply explaining your decision.
- Push the updated commits to the same branch — the PR updates automatically.
- Once the reviewer approves, a maintainer will merge the PR.

---

## Step 8 — Celebrate 🎉

Your first contribution is merged. You've completed the onboarding process.

Next steps:

- Pick up your next issue from the sprint board.
- Review a teammate's pull request to build familiarity with the codebase.
- Ask a lead about upcoming features or areas where the team needs help.

---

← Back to [PartSync Overview](index.md) | [Onboarding Index](../index.md)
