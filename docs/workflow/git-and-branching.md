# Git & Branching Strategy

---

### **Branch Naming Standard** 
Always branch off `main/master` (or the repository's designated default branch) using structured prefixes:
  - Features: `feature/#<id>-short-description` (e.g., `feature/#182-new-login-ui`)
  - Bug Fixes: `bugfix/#<id>-short-description` (e.g., `bugfix/#183-db-check-sqlite-crash`)
  - Chores / Maintenance: `chore/#<id>-short-description` (e.g., `chore/#184-update-documentation`)

---

### **Local Pre-Flight Checks**
Run test suites, type-checkers, and linters locally before pushing changes.

---

### **Pull Request Protocol**
  - Summarize the architectural or functional change.
  - Provide step-by-step verification instructions (how to run, reproduce, or inspect the change in local or staging environments).
  - Link the issue using `Closes #<id>` or `Fixes #<id>`.
  - Request at least one peer code review.

---

### **Merging into main/master**
When all automated checks and tests have passed:
  - Merge the Pull Request into main/master.
  - Delete the PR branch (both locally and on GitHub).

---
