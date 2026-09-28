# Coding Standards & Conventions

This document defines the core programming, naming, commit, and code organization conventions across all repositories in the **Machine Learning Thrive** project. Following these standards ensures code readability, modularity, and smooth onboarding for new interns.

---

## 1. Function Naming Best Practices

Function names must clearly communicate intent. Prefer explicit, descriptive names over short, ambiguous ones. Avoid vague names such as `doStuff()`, `handle()`, or generic one-letter variables.

* **Recommended:** `fetchUserProfile()`, `calculateTotalAmount()`, `validateFormInputs()`
* **Avoid:** `doStuff()`, `handleClick()`, `foo()`, `processData()`

> **Guidelines:**
> - **Use meaningful verbs:** Prefix functions with standard verbs indicating their action (e.g., `get`, `fetch`, `calculate`, `validate`, `format`).
> - **Avoid side effects:** Pure functions should produce predictable output based strictly on provided arguments without unintentionally mutating external state.
> - **Refactor early:** If a function's responsibility expands beyond a single clear purpose, decompose it into smaller helper functions.

---

## 2. Organizing Functions & Files

Maintain a structured hierarchy for custom business logic and utilities across both frontend and backend codebases.

### Component-Specific Functions
If a helper function is only needed within a single UI component or service module, keep it scoped locally inside that file. Do not expose internal details globally.

### Reusable Functions
Functions reused across multiple views, services, or components must be extracted into dedicated modular utility files categorized by domain.

Do not create an individual file for each tiny function. Group related utilities together logically:

```text
src/
├── api/
│   ├── userApi.js          # e.g., fetchUserData(), updateUserProfile()
│   └── authApi.js          # e.g., loginWithToken(), refreshSession()
└── utils/
    ├── arrayUtils.js       # e.g., filterArray(), sortArray()
    ├── dateUtils.js        # e.g., formatDate(), parseDate()
    └── formatters.js       # e.g., formatCurrency(), truncateString()
```

---


## 3. Comments & Code Structure

Keep source code self-documenting through clear variable and function names. Minimize inline comments—use them strictly to explain **why** a non-obvious choice was made, not **what** the code does.

For large files containing multiple architectural sections, use standard visual section markers to aid IDE navigation:

```typescript
// MARK: - User Authentication Functions
```
