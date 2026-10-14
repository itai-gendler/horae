---
kind: edge
routes:
  web: Web
steps:
- text: The Manager chooses Approve on a listed week
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::approvals
- text: The weekly timesheet is no longer awaiting approval
  kind: condition
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::approvals
- text: The Product reports that the week is not awaiting approval
  kind: product
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::approvals
---

# Approving a week that is no longer pending

## Trigger

A manager approves a week that someone else already reopened or approved.

## Outcome

Nothing changes and the manager is told the week is not awaiting approval.
