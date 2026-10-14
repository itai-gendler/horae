---
kind: edge
routes:
  web: Web
steps:
- text: The Member starts a timer
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: One of the Member's time entries is already running
  kind: condition
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Running]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses to start another timer
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
---

# Starting a second timer is refused

## Trigger

A person who already has a running timer starts another.

## Outcome

The first timer keeps running and no second entry is recorded.
