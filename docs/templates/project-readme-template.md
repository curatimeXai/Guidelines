![MLThrive Logo](../design/images/logoHigh.svg)

# Project Documentation Template

This document serves as the standard template for documenting repositories within The Machine Learning Thrive Project. It ensures a consistent onboarding experience, clear architecture overview, and structured guidelines for contributing developers and QA engineers.

To use this template, copy this file into your repository as `README.md` (or into `docs/`) and update the placeholders to reflect your project's specific setup.

---

## Table of Contents

- [Tech Stack](#tech-stack)
  - [Frontend (Client-Side)](#frontend-client-side)
  - [Backend (Server-Side)](#backend-server-side)
  - [Database](#database)
  - [Hosting & Deployment](#hosting--deployment)
  - [Testing](#testing)
  - [Development Tools](#development-tools)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Local Installation](#local-installation)
- [Design & Assets](#design--assets)
  - [Brand Colors & Theme](#brand-colors--theme)
- [Key Functions & Architecture](#key-functions--architecture)
- [Coding Standards & Conventions](#coding-standards--conventions)
  - [Function Naming](#function-naming)
  - [File & Code Organization](#file--code-organization)
  - [Commit Messages](#commit-messages)
  - [Code Comments](#code-comments)

---

## Tech Stack

Overview of the core technologies, libraries, and runtime environments powering this repository.

#### Frontend (Client-Side)
- **Languages:** TypeScript / JavaScript / HTML5 / CSS3
- **Framework & Libraries:** React / Next.js / Vue.js
- **State Management:** Zustand / Redux Toolkit
- **Styling:** Tailwind CSS / SCSS

#### Backend (Server-Side)
- **Runtime & Languages:** Python / Node.js / Java
- **Frameworks:** FastAPI / Express.js / Django
- **API Style:** REST / GraphQL

#### Database
- **Primary Database:** PostgreSQL / MySQL / SQLite
- **ORM / Query Builder:** SQLAlchemy / Prisma

#### Hosting & Deployment
- **Hosting Platforms:** DigitalOcean / AWS / Vercel
- **CI/CD:** GitHub Actions (Self-hosted runner)

#### Testing
- **Unit & Integration:** Pytest / Jest / JUnit
- **E2E & UI Testing:** Cypress / Selenium WebDriver

#### Development Tools
- **Package Managers:** npm / yarn / pnpm / poetry / pip
- **Linters & Formatters:** ESLint / Prettier / Ruff / Black

---

## Getting Started

### Prerequisites
List required software versions (e.g., Node.js >= 18.x, Python >= 3.11, Docker).

### Local Installation

1. **Clone the repository:**
   ```bash
   git clone <project-github-url>
   cd <project-directory>
   ```

2. **Configure environment variables:**
   ```bash
   cp .env.example .env
   ```

3. **Install dependencies:**
   ```bash
   npm install
   # or for Python backend:
   # pip install -r requirements.txt
   ```

4. **Initialize database / Seed data (if applicable):**
   ```bash
   python scripts/init_db.py
   ```

5. **Run the local development server:**
   ```bash
   npm run dev
   # or for backend:
   # uvicorn app.main:app --reload --port 8000
   ```

[Back to top](#table-of-contents)

---

## Design & Assets

Refer to the official design system in [Graphic Profile](docs/design/graphic-profile.md) for full typography and component styling rules.

### Brand Colors & Theme

| Role | Color Name | Hex / RGB | Usage |
| :--- | :--- | :--- | :--- |
| **Primary** | MLThrive Blue | `#0070F3` / `rgb(0, 112, 243)` | Primary CTAs, active links |
| **Success** | Forest Green | `#22C55E` / `rgb(34, 197, 94)` | Badges, success alerts |
| **Warning / Error** | Crimson Red | `#EF4444` / `rgb(239, 68, 68)` | Error messages, destructive actions |

[Back to top](#table-of-contents)

---

## Key Functions & Architecture

Document critical or custom architectural components here. Do not document standard framework boilerplate or trivial helper loops—focus on business logic, authentication handlers, or custom data pipelines.

When referencing source files, always provide relative links directly to the file (and line numbers where appropriate):
- Authentication store handler: [`AuthStore.tsx`](./src/stores/AuthStore.tsx)
- Custom user validation hook: [`useUserValidation.ts#L25`](./src/hooks/useUserValidation.ts#L25)

[Back to top](#table-of-contents)

---

## Coding Standards & Conventions

### Function Naming
Function names must clearly communicate intent. Prefer explicit, descriptive names over short, ambiguous ones. Avoid vague names such as `doStuff()`, `handle()`, or generic one-letter variables.

* **Recommended:** `fetchUserProfile()`, `calculateDiscountTotal()`, `validateRegistrationInput()`
* **Avoid:** `getData()`, `handleClick()`, `process()`

### File & Code Organization

* **Component-Scoped Logic:** If a helper function is only consumed by a single component, keep it scoped within that component's file.
* **Reusable Shared Logic:** Modularize reusable logic into dedicated utility or service modules grouped by domain:
  ```text
  src/
  ├── api/
  │   ├── authApi.ts
  │   └── userApi.ts
  └── utils/
      ├── dateUtils.ts
      └── formatters.ts
  ```
* **Pure Functions:** Aim for deterministic functions with clear inputs and return values. Avoid unexpected mutations of external state.

### Commit Messages
Write commit messages in the **imperative present tense** (`Add feature`, not `Added feature` or `Adds feature`). Keep the subject line concise (under 72 characters).

* **Good:** `Add user authentication validation to login endpoint`
* **Good:** `Fix CORS header configuration on staging route`
* **Bad:** `Added user authentication`
* **Bad:** `Fixing stuff`

#### Co-Authoring Commits
When collaborating or pairing on tasks, credit co-authors at the end of the commit body:
```text
Co-authored-by: Collaborator Name <collaborator@example.com>
```

### Code Comments
Keep comments focused on **why** something was done rather than **what** the code does. Code should remain self-documenting through clean variable and function naming.

Use standard section markers to partition large files for IDE navigation:
```typescript
// MARK: - Authentication Handlers
```

[Back to top](#table-of-contents)
