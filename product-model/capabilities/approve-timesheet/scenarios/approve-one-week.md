---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Approve on a weekly timesheet awaiting approval
  kind: actor
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: [Week, Total time]}
  contexts:
    web:
      place: web::team::approvals
- text: The Product approves the weekly timesheet, recording the approver and time
  kind: product
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: changes, from: Awaiting approval, to: Approved, facts: [Approved by, Approved at]}
  contexts:
    web:
      place: web::team::approvals
- text: The Product approves every submitted time entry in that week
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: changes, from: Submitted, to: Approved, facts: []}
  contexts:
    web:
      place: web::team::approvals
---

# Approve one week

## Trigger

A manager chooses Approve on a pending week.

## Outcome

The week is approved, recording who approved it and when, and its submitted time is approved.
