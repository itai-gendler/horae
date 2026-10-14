---
kind: alternative
routes:
  web: Web
steps:
- text: The Member clears a filled day cell
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product removes the time entry behind the cell
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: removes, from: Open}
  contexts:
    web:
      place: web::team::timesheet
---

# Clear a week cell

## Trigger

A person sets a filled day cell in the week view to zero.

## Outcome

That day's time entry for the row is deleted.
