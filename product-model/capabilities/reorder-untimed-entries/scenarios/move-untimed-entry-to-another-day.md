---
kind: alternative
routes:
  web: Web
steps:
- text: The Member drags an open untimed entry onto another day
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product saves the new date and positions
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Date, Position]}
  contexts:
    web:
      place: web::team::timesheet
---

# Move an untimed entry to another day

## Trigger

A person drags an open untimed entry onto another day's stack.

## Outcome

The entry belongs to the new day at the chosen place.
