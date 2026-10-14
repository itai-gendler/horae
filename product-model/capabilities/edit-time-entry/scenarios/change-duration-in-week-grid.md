---
kind: alternative
routes:
  web: Web
steps:
- text: The Member types a new duration over a filled day cell
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product saves the new duration on that time entry
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Duration]}
  contexts:
    web:
      place: web::team::timesheet
---

# Change a duration in the week grid

## Trigger

A person types a new duration over an existing day cell in the week view.

## Outcome

The entry keeps its project task and notes with the new duration.
