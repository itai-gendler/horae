---
kind: edge
routes:
  web: Web
steps:
- text: The Member tries to drag a locked time entry
  kind: actor
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The time entry is not open
  kind: condition
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the move
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
---

# Moving a locked entry is refused

## Trigger

A person tries to drag an entry that is submitted, approved or invoiced.

## Outcome

The entry stays where it was and the calendar says it cannot be moved.
