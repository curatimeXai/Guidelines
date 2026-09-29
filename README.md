# 💊🫀 MLThrive 🏫📕

Welcome to the central hub of the **Machine Learning Thrive** project, led by Johannes Gutenberg University Mainz.

This repository defines the development and QA standards across all repositories, including task tracking, 
Git branching conventions, bug reporting, and project board management.

---

## Quick Navigation

| Section | Key Topics & Documents | Primary Audience |
| :--- | :--- | :--- |
| **[Workflow](docs/workflow/)** | [Git & Branching](docs/workflow/git-and-branching.md), [Board Lifecycle](docs/workflow/work-lifecycle-and-board.md), and [Submitting Work](docs/workflow/submitting-work-items.md). | All Team Members |
| **[Standards](docs/standards/)** | [Coding Standards](docs/standards/coding-standards.md) and [Development Tools / Live Share](docs/standards/development-tools.md). | Developers |
| **[Design](docs/design/)** | [Graphic Profile](docs/design/graphic-profile.md), typography, brand colors, and assets. | Frontend & UI/UX |
| **[DevOps](docs/devops/)** | [SSH Backend Access](docs/devops/ssh-backend-access.md) and [GitHub Actions Runner](docs/devops/github-actions-runner.md). | Backend & DevOps |
| **[Templates](docs/templates/)** | [Project README](docs/templates/project-readme-template.md), [Sprint Planning](docs/templates/sprint-planning-template.md), and Issue forms (bug, feature, task). | All Team Members |

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
