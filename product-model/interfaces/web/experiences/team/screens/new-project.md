---
entities:
- entity: project
  shows: &id001
  - Name
  - Code
  - Dates
  - Tags
  - Notes
  - Currency
  - Project type
  - Billing rates
  - Budget
  - Budget alert
  - Fees
  - Invoice defaults
  - Report visibility
  collects: *id001
- entity: client
  shows:
  - Name
  - Currency
  - Default rate
  collects:
  - Name
  - Currency
  - Default rate
- entity: task
  shows:
  - Name
  - Archived
  collects:
  - Name
- entity: project-task
  shows:
  - Billable
  - Hourly rate
  - Budget
  - Access
  - Selected people
  collects:
  - Billable
  - Hourly rate
  - Budget
  - Access
  - Selected people
- entity: team-membership
  shows:
  - Project role
  - Billable rate
  - Cost rate
  - Budget
  collects:
  - Project role
  - Billable rate
  - Cost rate
  - Budget
- entity: account
  shows:
  - Name
- entity: project-draft
  shows:
  - Saved at
entryPoints:
- web: /projects/new
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project.rs
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project/basics.rs
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project/billing.rs
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project/tasks.rs
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project/team.rs
---

# New project

The form where a manager or admin sets up a new project, kept as a private draft until it is saved.
