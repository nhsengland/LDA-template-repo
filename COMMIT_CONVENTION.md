# 📘 Commit Convention Guide

### 🧭 Purpose
This document defines our **Git commit standards** to ensure a clear, consistent, and maintainable project history.  
Good commit hygiene improves collaboration, simplifies code reviews, enables automated changelogs, and makes debugging easier.

---

## 🧱 Commit Message Format

Each commit message **MUST** follow this structure:

```
<type>(<scope>): <short summary>

[optional body]

[optional footer]
```

### Example

```
feat(api): add pagination to patient list endpoint

Adds pagination support to improve performance when listing large datasets.
Includes unit tests and updates API documentation.

Closes #245
```

---

## ✍️ 1. Message Header

The header is a single line that contains:
- a **type** (required)
- a **scope** (optional)
- a **short summary** (required)

### Format
```
<type>(<scope>): <summary>
```

### ✅ Rules
- Use **imperative mood**: “add” not “added” or “adds”.
- Keep the summary under **72 characters**.
- Don’t end with a period.

---

## 🧩 2. Commit Types

| Type | Purpose |
|------|----------|
| **feat** | Introduces a new feature |
| **fix** | Fixes a bug |
| **docs** | Documentation-only changes |
| **style** | Formatting or style changes (no logic impact) |
| **refactor** | Code restructure without changing behavior |
| **perf** | Performance improvements |
| **test** | Adds or modifies tests |
| **build** | Build system or dependency changes |
| **ci** | Continuous integration or deployment changes |
| **chore** | Routine maintenance (e.g., version bumps) |
| **revert** | Reverts a previous commit |

---

## 🧭 3. Scope (Optional)

Use the **scope** to indicate the area of the project affected.

Examples:
- `api`, `ui`, `db`, `auth`, `docs`, `infra`, etc.

Example:
```
fix(auth): handle expired JWT token
```

---

## 💬 4. Body (Optional but Recommended)

Use the body to explain:
- **What** the change does.
- **Why** the change was made.
- Any relevant **context or caveats**.

Example:
```
The login API previously failed silently when tokens expired.
This adds proper error handling and client notification.
```

---

## 🔗 5. Footer (Optional)

Use for:
- Breaking changes
- Issue references
- Related tasks

Examples:
```
BREAKING CHANGE: renamed `userId` to `accountId` in API response.
Closes #123
Refs #456
```

---

## 🧼 Commit Hygiene Rules

### ✅ DO:
- Keep each commit **focused** on a single logical change.
- **Commit often**, but only when tests pass.
- **Reference issues or tickets** in your footer.
- **Rebase interactively** (`git rebase -i`) to squash cleanup commits before merging.
- Write **clear, readable messages** for future maintainers.

### ❌ DON’T:
- Mix unrelated changes in one commit.
- Commit generated or build artifacts (`dist/`, `node_modules/`, etc.).
- Rewrite shared/public history unless absolutely necessary.
- Use vague messages like “fix stuff” or “update code”.

---

## 🧾 Example Commit History

```
feat(api): add patient search endpoint
feat(ui): implement search bar component
fix(ui): debounce search input to prevent API spam
docs: update README with new search feature
refactor(api): extract common query builder
```

---

## 🧾 Quick Reference

| Example | Description |
|----------|--------------|
| `feat(ui): add dark mode toggle` | New feature |
| `fix(api): handle null user input` | Bug fix |
| `docs(readme): add setup instructions` | Documentation |
| `style(css): adjust button spacing` | Style-only change |
| `refactor(auth): simplify token validation` | Code improvement |
| `perf(api): cache patient data` | Performance |
| `test(api): add pagination tests` | Tests |
| `chore(deps): bump react to 18.3.0` | Maintenance |
