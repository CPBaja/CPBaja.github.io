# Starting an Issue

This guide outlines the process for selecting an issue from the project board, assigning it to yourself, creating a linked branch, and moving the issue to **In progress**.

---

## 1. Identify an Issue Ready to Be Picked Up
1. Navigate to the **Software Project Board** on GitHub.
2. Look for items in the **Sprint** column.
3. Select an issue that:
   - Is unassigned
   - Has clear requirements
   - Fits your skill set

---

## 2. Assign Yourself to the Issue
1. Open the issue.
2. In the right-hand sidebar, find **Assignees**.
3. Click **Assign yourself**.

This signals that the issue is taken and avoids duplicate work.

---

## 3. Create a Branch From the Issue Page
Always create the branch using GitHub’s **Development** section on the issue page to ensure linking and proper cross-referencing.

1. Locate the **Development** section in the issue.
2. Click **Create a branch**.
3. Use the required naming convention:

   ```
   issue-<issue-number>
   ```

   Example:

   ```
   issue-69
   ```

4. Confirm creation. GitHub will link the branch to the issue automatically.

---

## 4. Move the Issue to "In progress"
After assigning yourself and creating the branch:

1. Return to the **Project Board**.
2. Drag the issue card from **Sprint** to **In progress**.
3. Verify your avatar appears on the card.

---

## 5. Begin Work on the Branch
Pull the branch locally:

```sh
git fetch
git checkout issue-69
```

Follow organization standards for commits, documentation, and pull requests.
