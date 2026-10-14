---
entities:
- entity: project
  shows:
  - Name
  - Code
  - Dates
  - Tags
  - Notes
  - Currency
  - Budget progress
  - Fee balance
- entity: client
  shows:
  - Name
- entity: project-task
  shows:
  - Billable
- entity: task
  shows:
  - Name
- entity: team-membership
  shows:
  - Project role
- entity: account
  shows:
  - Name
entryPoints:
- web: /projects/:id
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/projects.rs#ProjectDetail
- kind: code
  role: implementation
  target: crates/horae/src/pages/projects/fee_balances.rs
---

# Project

One project's details, its tasks and team, its budget progress and its fee balances.
