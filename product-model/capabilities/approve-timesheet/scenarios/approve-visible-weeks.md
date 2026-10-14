---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager chooses Approve visible timesheets
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::approvals
- text: The Product approves each listed weekly timesheet still awaiting approval
  kind: product
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: changes, from: Awaiting approval, to: Approved, facts: [Approved by, Approved at]}
  contexts:
    web:
      place: web::team::approvals
- text: The Product approves the submitted time entries of those weeks
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: changes, from: Submitted, to: Approved, facts: []}
  contexts:
    web:
      place: web::team::approvals
---

# Approve every visible week

## Trigger

A manager chooses Approve visible timesheets while pending weeks are listed.

## Outcome

Every listed week that is still pending is approved at once.

## Edge cases

- Weeks that were reopened or approved by someone else meanwhile are skipped.
