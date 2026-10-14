---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager chooses Reopen on an approved weekly timesheet
  kind: actor
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: [Week]}
  contexts:
    web:
      place: web::team::approvals
- text: The Product reopens the week's approved time entries and clears their rounded durations
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: changes, from: Approved, to: Open, facts: [Rounded duration]}
  contexts:
    web:
      place: web::team::approvals
- text: The Product removes the weekly timesheet
  kind: product
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: removes, from: Approved}
  contexts:
    web:
      place: web::team::approvals
---

# Reopen an approved week

## Trigger

A manager chooses Reopen on an approved week.

## Outcome

The approval is undone and the week's approved time is open again.

## Edge cases

- Invoiced time in the week stays invoiced.
