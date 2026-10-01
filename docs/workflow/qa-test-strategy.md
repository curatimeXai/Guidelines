# QA Test Strategy & Verification Process

> Unified quality assurance workflow, testing tiers, and Definition of Done (DoD) verification standards.

---

## 1. Objectives & Scope

The purpose of this strategy is to establish a unified QA standard across the engineering team, streamline onboarding, prevent issues from being closed prematurely without QA validation, and maintain high release confidence.

Every feature, bug fix, and configuration change targeted for merge into `master` (or `main`, depending on which branch is your projects default) must satisfy the verification levels outlined below.

---

## 2. Testing Tiers & Coverage

Testing is categorized into three sequential tiers to provide broad coverage while preserving fast feedback loops:

| Tier | Focus Area | Tools & Execution | Scope & Trigger |
| :--- | :--- | :--- | :--- |
| **Tier 1: Frontend Smoke Checks** | Route navigation, responsive rendering, component state changes, and error boundary handling. | Manual inspection on local development server or **AWS Amplify Pull Request Previews**. | Every pull request containing frontend modifications. |
| **Tier 2: Automated API Regression** | Endpoint contract stability, response status codes, payload structure, token validation, and error schemas. | **Postman / Newman** test suites (`tests/postman`) against local or staging endpoints. | Every API change and pre-merge regression run. |
| **Tier 3: Exploratory & Integration** | Cross-feature user workflows, audio/external API integrations, edge-case validation, and data persistence. | Manual exploratory testing charters and integration checkpoints. | Complex features, major bug fixes, and pre-release audits. |

---

## 3. Bug Verification Lifecycle

All bug reports and feature tasks follow a structured status transition across the project board to prevent unverified closures:

```text
[ In Progress ]
       │
       │  (Developer completes code, opens PR, confirms build passes)
       ▼
[ In Review ]
       │
       │  (QA executes test scenarios on preview environment)
       ├──────────────────────────────┐
       │                              │
       ▼ (Fails verification)         ▼ (Passes verification)
[ Ready ]                      [ Done ]
  - Add reproducible comment     - Document test evidence (logs/screenshots)
  - Reassign to author           - Approve PR / Move issue to Done
```

### Transition Guidelines:
1. **Developer Handoff:** When development is complete, the author links the Pull Request to the issue and transitions the card from `In Progress` to `In Review`. Developers must never close issues directly without QA sign-off.
2. **QA Verification:** A QA engineer pulls the latest branch or navigates to the active Amplify live preview URL to perform regression checks and target verifications.
3. **If Verification Fails:** Transition the issue to `Ready`, reassign the issue to the developer, and leave a comment outlining:
   - Reproduction steps
   - Expected behavior vs. actual behavior
   - Environment / commit hash tested
   - Supporting screenshots, network logs, or console errors
4. **If Verification Passes:** Approve the pull request and move the card to `Done`.

---

## 4. Pull Request & Definition of Done (DoD) Alignment

An issue or PR is formally considered **Done** only when all the following criteria are met:

- [ ] **Automated CI Checks Pass:** GitHub Actions workflows (Gitleaks, linting, frontend builds) succeed without bypass.
- [ ] **API Regression Verified:** Postman collection runs clean with 0 test failures for affected and dependent endpoints.
- [ ] **Acceptance Criteria Validated:** All acceptance criteria specified in the GitHub issue are verified by QA.
- [ ] **No Security Leaks:** The commit history and diff contain no sensitive keys, passwords, or untracked environment secrets.
- [ ] **QA Approval:** Pull request is reviewed and approved by QA prior to merge.
- [ ] **Branch Cleanup:** The source feature/bugfix branch is deleted from GitHub immediately upon merging.
- [ ] **Documentation Updated:** Technical guides, architectural changes, or new endpoints are reflected in `docs/`.

---
