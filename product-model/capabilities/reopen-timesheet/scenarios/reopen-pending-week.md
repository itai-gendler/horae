---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Reopen on a weekly timesheet awaiting approval
  kind: actor
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: [Week]}
  contexts:
    web:
      place: web::team::approvals
- text: The Product reopens the week's submitted time entries and clears their rounded durations
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: changes, from: Submitted, to: Open, facts: [Rounded duration]}
  contexts:
    web:
      place: web::team::approvals
- text: The Product removes the weekly timesheet
  kind: product
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: removes, from: Awaiting approval}
  contexts:
    web:
      place: web::team::approvals
---

# Reopen a week awaiting approval

## Trigger

A manager chooses Reopen on a pending week.

## Outcome

The week leaves Approvals and its time is open and editable again, without its frozen rounding.
