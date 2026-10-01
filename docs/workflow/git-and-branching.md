# Git & Branching Strategy

---

### **Single Source of Truth**
Never create or track manual IDs. Every task, feature, enhancement, and defect is tracked exclusively by its GitHub Issue number (e.g., #182).

---

### Branch Naming Standard

Always branch off `main`/`master` (or the repository's designated default branch) using structured prefixes that mirror our commit conventions:

| Prefix | Commit Type | Purpose | Example |
| :--- | :--- | :--- | :--- |
| `feature/` | `feat:` | New feature or functional enhancement | `feature/#182-new-login-ui` |
| `fix/` | `fix:` | Bug fixes and defect corrections | `bugfix/#183-sqlite-crash` |
| `docs/` | `docs:` | Documentation updates only | `docs/#184-qa-test-strategy` |
| `refactor/` | `refactor:` | Code restructuring without feature changes | `refactor/#190-auth-service` |
| `style/` | `style:` | CSS, styling, or UI adjustments | `style/#195-button-spacing` |
| `chore/` | `chore:` | Build configs, CI/CD, or dependencies | `chore/#201-bump-deps` |

#### Format Rules:
* Use lowercase letters and kebab-case for the description (`just-like-this`).
* Reference the issue ID directly in the branch name (`#<id>`).
* Branch format: `<prefix>/#<id>-<short-description>`

---

### **Commit Message Standards**
Commit messages must be written in the imperative present tense and always reference the issue ID using Conventional Commits format:

    Format: (#): 

    Examples:

        feat(#183): implement dark mode toggle

        fix(#182): resolve sqlite dialect compatibility in /db-check

        chore(#184): update documentation and badges

---

### **Local Pre-Flight Checks**
Run test suites, type-checkers, and linters locally before pushing changes.

---

### **Pull Request Protocol & Automated Closure**
  - **PR Description** 
  Summarize architectural or functional changes and provide step-by-step verification instructions.
  - **Link the Issue** 
  Always link the issue directly using GitHub closing keywords (e.g., Closes #182, Fixes #182) to guarantee the issue closes automatically upon merge.
  - **Code Review** 
  Request at least one peer review.

---

### **Merging into main/master**
When all automated checks and tests have passed:
  - Merge the Pull Request into main/master.
  - Delete the PR branch (both locally and on GitHub).

---
