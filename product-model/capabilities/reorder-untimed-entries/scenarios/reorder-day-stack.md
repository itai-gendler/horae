---
kind: primary
routes:
  web: Web
steps:
- text: The Member drags an untimed entry to a new place in the day's stack
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product saves each untimed entry's new position
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Position]}
  contexts:
    web:
      place: web::team::timesheet
---

# Reorder a day's untimed entries

## Trigger

A person drags an untimed entry above or below another on the same day.

## Outcome

The day's untimed entries keep the new order.
