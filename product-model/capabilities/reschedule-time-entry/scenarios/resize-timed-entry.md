---
kind: alternative
routes:
  web: Web
steps:
- text: The Member drags the edge of a timed entry
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product saves the new duration
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Duration]}
  contexts:
    web:
      place: web::team::timesheet
---

# Resize a timed entry on the calendar

## Trigger

A person drags the edge of one of their open timed entries.

## Outcome

The entry keeps its start and has the new duration.
