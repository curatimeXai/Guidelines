# 💊🫀 MLThrive 🏫📕

Welcome to the central hub of the **Machine Learning Thrive** project, led by Johannes Gutenberg University Mainz.

This repository defines the development and QA standards across all repositories, including task tracking, 
Git branching conventions, bug reporting, and project board management.

---

## Quick Navigation

| Section | Topic | Primary Audience |
| :--- | :--- | :--- |
| **[1. Traceability & References](docs/workflow/traceability-and-references.md)** | Single source of truth, Issue IDs, and PR linking keywords. | Developers & QA |
| **[2. Git & Branching Strategy](docs/workflow/git-and-branching.md)** | Branch conventions, pre-flight checks, and PR guidelines. | Developers |
| **[3. Work Lifecycle & Execution](docs/workflow/work-lifecycle-and-board.md)** | End-to-end task progression (Sprints & Kanban). | All team members |
| **[4. Board Columns & Definitions](docs/04-board-columns-and-statuses.md)** | Status mapping from Backlog to Done/Invalid. | All team members |
| **[5. Submitting Work Items](docs/workflow/submitting-work-items.md)** | How to report bugs and create feature requests/tasks. | QA & Developers |
| **[6. DevOps & Infrastructure](docs/devops/github-actions-runner.md)** | How to report bugs and create feature requests/tasks. | DevOps & Infrastructure admins |

---

## Core Principles at a Glance

* **Issue ID as Single Source of Truth:** Never create manual IDs. Reference the GitHub Issue number (`#<id>`) in commits, PRs, and chats.
* **Shift-Left Quality:** Run local linters, type checks, and tests before pushing code.
* **Traceable Commits & Closures:** Always use closing keywords in PRs (e.g., `Closes #182` or `Fixes #182`) to keep boards synchronized automatically.
* **Verified Deliveries:** Work is only moved to `Done` once verified by QA against reproduction steps or Acceptance Criteria.

---

## Getting Started

1. **Working on a task?** Review [Git & Branching Strategy](docs/workflow/git-and-branching.md) for branch naming conventions.
2. **Reporting an issue?** Check [Submitting Work Items](docs/workflow/submitting-work-items.md) to ensure mandatory fields are filled out.
3. **Updating the board?** Consult [Board Columns & Definitions](docs/04-board-columns-and-statuses.md) for column transition rules.
---


For any questions, feel free to open an issue or contact the project coordinator.

Lovisa Blomster - lovisablomster@gmail.com  
*The MLThrive Team*
