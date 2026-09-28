# 💊🫀 MLThrive 🏫📕

Welcome to the central hub of the **Machine Learning Thrive** project, led by Johannes Gutenberg University Mainz.

This repository defines the development and QA standards across all repositories, including task tracking, 
Git branching conventions, bug reporting, and project board management.

---

## Quick Navigation

| Section | Topic | Primary Audience |
| :--- | :--- | :--- |
| **[Git & Branching](docs/workflow/git-and-branching.md)** | Branch conventions, commit standards, and PR workflows. | All Developers |
| **[Work Lifecycle & Board](docs/workflow/work-lifecycle-and-board.md)** | Task flow across board columns from Backlog to Done. | All Team Members |
| **[Submitting Work Items](docs/workflow/submitting-work-items.md)** | Guidelines for logging bugs, tasks, and feature requests. | QA & Developers |
| **[Coding Standards](docs/standards/coding-standards.md)** | Function naming, clean architecture, and modular code rules. | Developers |
| **[Development Tools](docs/standards/development-tools.md)** | Recommended VS Code extensions and Live Share pairing. | All Team Members |
| **[Graphic Profile](docs/design/graphic-profile.md)** | Official typography, brand colors, and UI theme assets. | Frontend & Design |
| **[DevOps & Server Access](docs/devops/ssh-backend-access.md)** | SSH backend access, key setup, and [GitHub Runner setup](docs/devops/github-actions-runner.md). | Backend & DevOps |
| **[Project Template](docs/templates/project-readme-template.md)** | Standard README documentation template for new services. | Project Leads & Devs |

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
