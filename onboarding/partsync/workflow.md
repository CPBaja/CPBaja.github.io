# 🔄 PartSync Contribution Workflow

This page describes the contribution workflow for the PartSync (Parts-Management) repository. Follow these conventions on every piece of work you contribute.

---

## Branching Strategy

### Protected Branches

The `main` branch is **protected**. You cannot push directly to it. All changes must go through a pull request.

### Feature Branch Naming

Always create your branch from the issue page (see [Starting an Issue](../../BestPractices/StartingAnIssue.md)). Use the following naming convention:

```
issue-<issue-number>
```

**Example:**

```
issue-42
```

Creating the branch from the issue page automatically links the branch to the issue for cross-referencing.

---

## Pull Request Process

### Naming Convention

Use the following format for PR titles:

```
Issue #<number> <commit-style-message>
```

**Example:**

```
Issue #42 Add filter by subassembly to catalog view
```

### Opening a PR

1. Push your feature branch to the remote.
2. Navigate to the repository's **Pull Requests** tab on GitHub.
3. Click **New pull request**.
4. Set your feature branch as the source and `main` as the target.
5. Title the PR using the naming convention above.
6. Write a concise description of what changed and why.
7. Assign a reviewer from the team.

See the full guide: **[Opening a Pull Request](../../BestPractices/OpeningAPullRequest.md)**

### Required Review

Every PR requires **at least one approved review** before it can be merged. The reviewer will check for:

- Correctness and completeness
- Adherence to code standards
- No regressions or broken tests

---

## Issue Labels

The following labels are used in the PartSync repository:

| Label | Description |
|-------|-------------|
| `bug` | Something isn't working |
| `enhancement` | New feature or request |
| `refactor` | Restructure code without changing behavior |
| `good first issue` | A well-scoped task suitable for new contributors |

When creating or updating an issue, apply the most relevant label.

---

## Code Standards

### Frontend (JavaScript)

- **Formatter**: Prettier — run `npm run format` before committing.
- **Linter**: ESLint — run `npm run lint` to check, `npm run lint:fix` to auto-fix.
- Format on save is configured in `.vscode/settings.json`. Enable it in VSCode.

**Prettier Options in Use:**

| Option | Value | Effect |
|--------|-------|--------|
| `jsxBracketSameLine` | `true` | Closing `>` of multi-line JSX stays on the last line |
| `endOfLine` | `"auto"` | Preserves existing line endings |

### Backend (Python)

- **Style checker**: PyCodeStyle — install with `pip install pycodestyle`.
- **Linter**: PyLint — enable linting in VSCode via the **Python: Enable Linting** command.
- Enable linting in `.vscode/settings.json`:

```json
{
  "python.linting.enabled": true,
  "python.linting.lintOnSave": true
}
```

### Naming Conventions

Follow standard conventions for each language:

- **JavaScript**: `camelCase` for variables and functions, `PascalCase` for React components.
- **Python**: `snake_case` for variables and functions, `PascalCase` for classes.

### Commit Message Format

Follow the team-wide [Commit Standards](../../BestPractices/CommitStandards.md):

- Use imperative mood: `Add`, `Fix`, `Refactor`
- Capitalize the first word
- Reference the issue number at the start

```
#42 Add filter by subassembly to catalog view
```

---

## Rebasing Policy

We maintain a linear Git history. **Do not merge `main` into your feature branch.** Instead, rebase onto `main`:

```bash
git fetch
git rebase --onto origin/main <parent-commit-hash>
```

`<parent-commit-hash>` is the commit on `main` where your branch originally diverged. See the full guide for a detailed walkthrough: **[Rebasing Guide](../../BestPractices/RebasingGuide.md)**

---

← Back to [PartSync Overview](index.md) | [Onboarding Index](../index.md)
