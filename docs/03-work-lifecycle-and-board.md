# Work Lifecycle & Board Execution
*Whether your project operates via fixed iterations (Sprints) or continuous flow (Kanban), items follow a standardized lifecycle across the project board:*  

---

### **Backlog / Prioritization**
- All triaged tasks and defect reports enter `Backlog`.
- Project leads, product owners, or team members continuously order items by business priority.

---

### **Committing to Work (Ready)**
- Items move from `Backlog` to `Ready` once specifications, reproduction steps, or acceptance criteria are clear.
- In iterative projects, `Ready` reflects the committed scope for the cycle. In continuous delivery projects, `Ready` serves as the prioritized next-up queue.

---

### **Active Development**  
Assign yourself (`Assignee`), update the item to `In Progress`, and open a corresponding branch.

---

### **Review & Verification**
- Pull Request
  *Open a PR, link the issue, and transition the item to `In Review`.*
- Peer Review
  *Engineers review code structure, performance, and test coverage.*
- QA / Verification
  *QA or a secondary reviewer validates the build against original defect steps or Acceptance Criteria.*
- Pass
  *PR is merged, the issue closes, and the card transitions to `Done`.*
- Fail / Changes Requested
  *Item reverts to `In Progress` with documented reproduction feedback*


---

### **Invalid / Superseded Items**
Items identified as duplicate, unreproducible, obsolete, or functioning as designed move to Invalid and are closed with an explanatory rationale.

---

# Board Columns & Status Definitions

| **COLUMN** | **DESCRIPTION & WORKFLOW ROLE** |
| :--- | :--- |
| **Backlog** | Ingestion pool. All newly created, triaged issues and tasks reside here awaiting prioritization. |
| **Ready** | Committed work scope. Well-defined work items ready to be picked up immediately. |
| **In Progress** | Active implementation. A developer has assigned themselves (`Assignee`) and begun investigation, coding, or testing. |
| **In Review** | Implementation complete. PR is open for peer review, or build is deployed to the test environment for QA verification. |
| **Done** | Verified and delivered. Task/fix has been verified by QA, code is merged into the target branch, and the issue is closed. |
| **Invalid** | Duplicate submissions, non-reproducible items, dropped features, or behaviors determined to be working as intended. |

---
