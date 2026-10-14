---
kind: edge
routes:
  web: Web
steps:
- text: The Member drags a running time entry onto another day
  kind: actor
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Running]}
  contexts:
    web:
      place: web::team::timesheet
- text: The time entry is running
  kind: condition
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Running]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the rearrangement
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
---

# Moving a running timer to another day is refused

## Trigger

A person drags the entry of a running timer onto another day.

## Outcome

The whole rearrangement is refused and nothing moves.
