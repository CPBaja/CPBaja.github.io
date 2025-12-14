# Rebasing Guide

We maintain a **clean, linear Git history** by rebasing feature branches onto `main` rather than merging `main` into them. This guide explains why we use rebase, how to apply it in our workflow, and how to keep branches aligned with `main` using `git rebase --onto`.

Rebasing keeps our history linear, reduces noise in PRs, and makes the repository easier to understand and maintain.

---

## 1. Why We Rebase

### What happens when you merge `main` into your branch

```bash
git merge origin/main
```

This introduces merge commits that clutter history and make tools like `git log` and `git bisect` harder to interpret.

### What happens when you rebase onto `main`

```bash
git fetch
git rebase --onto origin/main <parent-commit-hash>
```

Rebase **replays** your branch's commits on top of up‑to‑date `main`, producing a clear, linear history.

**Rule:** Always rebase your feature branch onto `main`. Do **not** merge `main` into feature branches.

---

## 2. Rebase Workflow

We primarily use `git rebase --onto` because target branches frequently change histories.

### General form

```bash
git rebase --onto <new-base> <old-base>
```

Git will:

- Take all commits on the current branch **after** `<old-base>`
- Replay them on top of `<new-base>`

### Example: Move a feature branch onto `main`

```bash
git fetch
git rebase --onto origin/main <parent-commit-hash>
```

This moves your feature branch so it now sits directly on top of `main`.

### Conflict Resolution

If conflicts occur:

1. Resolve conflicts using GitHub Desktop and VS Code.
2. If you are **not confident** in how to resolve a conflict safely, **ask for support before proceeding**. Rebasing rewrites history, so it is better to pause and get help than to risk breaking the branch.
