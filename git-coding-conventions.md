
# Git Conventions and Best Practices

This document outlines the essential Git conventions and best practices to maintain a clean, structured project history. By adhering to these guidelines, we ensure project consistency and facilitate easier navigation through Git history, especially for long-term project maintenance.

## Branch Structure

### Production & Development Branches

Our primary branches are:

- **production** ➝ Release branch used in production.
- **development** ➝ Mirror of production, containing the last stable changes.
- **staging** ➝ Dev branch for testing and validation in the staging environment.

---

## New Branches & Naming Conventions

Each new feature or hotfix begins on a new branch. **Avoid** committing directly to `production`, `development`, or `staging`. Follow these naming conventions:

- **feature/** ➝ For new features (requires a related ticket in the issue tracker).
- **hotfix/** ➝ For bug fixes (also requires a related ticket).

**Branch Creation Example:**

- Checkout from `development` for features, and from `production` for hotfixes:

  ```bash
  git checkout -B <branch-name>
  ```

- Use descriptive, relevant branch names; matching ticket names when possible. Correct Examples:

  ```bash
  git checkout -B feature/rolling-balance-integration
  git checkout -B feature/player-levelup
  git checkout -B hotfix/levelup-reward-fix
  git checkout -B hotfix/mileage-distribution-command-fix
  ```

- Avoid using names like these:

  ```bash
  git checkout -B feature/rollingBalanceIntegration
  git checkout -B player-levelup
  git checkout -B levelup-reward-fix
  git checkout -B hotfix/mileageDistributionCommandFix
  ```

### Workflow

For a **feature**:

```bash
git checkout development
git pull origin development
git checkout -B feature/xyz-implementation
```

For a **hotfix**:

```bash
git checkout production
git pull origin production
git checkout -B hotfix/xyz-fix
```

---

## Adding Files to Commits

Before committing, review changes to ensure only intended updates are included. Use the following commands for review:

```bash
git status             # Shows untracked changes
git diff               # Shows code differences
git diff --name-only   # Shows only file names with changes
git add . -p           # Allows you to add changes line by line (recommended)
```

**Avoid** using `git add .` as it stages all changes without review.

---

## Commit Messages

Consistent, clear commit messages help maintain a focused change history. Examples of structured commit messages:

```bash
git commit -m "Feature: XYZ CRUD Done"
git commit -m "Feature: XYZ Services & Models Done"
git commit -m "Feature: XYZ Refactor & Improvements"
git commit -m "Feature: XYZ Tests Done"
git commit -m "Feature: XYZ Final Touches"
```

---

## Important Considerations

- **Pre-Push Testing**: Test code thoroughly before pushing to avoid introducing incomplete or broken code.
- **Regular Rebasing**: Rebase your branch regularly with `development` to stay updated with recent changes. This minimizes conflicts and eases merging.

---

## Things to Avoid

- **Avoid Pushing Broken Code**: Do not push incomplete or broken code to remote branches. Commit locally or stash incomplete work, but keep remote branches clean and stable for team access.

---

By following these conventions, we ensure a reliable and navigable Git history for the entire team.
