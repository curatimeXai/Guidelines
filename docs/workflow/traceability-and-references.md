# Traceability & Issue Referencing

---

### **Single Source of Truth**
Never create or track manual IDs. Every task, feature, enhancement, and defect is tracked exclusively by its GitHub Issue number (e.g., #182).

---

### **Automated Closures via PR**
Developers must link issues directly in Pull Request descriptions using standard GitHub closing keywords (e.g., Closes #182, Fixes #182). 
This guarantees the issue closes automatically upon merge.

---

### **Commit Traceability**
Reference the issue ID in commit messages:
  * `feat(#183): implement dark mode toggle`
  * `fix(#182): resolve sqlite dialect compatibility in /db-check`

---
