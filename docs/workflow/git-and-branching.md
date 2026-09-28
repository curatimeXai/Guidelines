# Git & Branching Strategy

---

### **Single Source of Truth**
Never create or track manual IDs. Every task, feature, enhancement, and defect is tracked exclusively by its GitHub Issue number (e.g., #182).

---

### **Branch Naming Standard** 
Always branch off `main/master` (or the repository's designated default branch) using structured prefixes:
  - Features: `feature/#<id>-short-description` (e.g., `feature/#182-new-login-ui`)
  - Bug Fixes: `bugfix/#<id>-short-description` (e.g., `bugfix/#183-db-check-sqlite-crash`)
  - Chores / Maintenance: `chore/#<id>-short-description` (e.g., `chore/#184-update-documentation`)

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
