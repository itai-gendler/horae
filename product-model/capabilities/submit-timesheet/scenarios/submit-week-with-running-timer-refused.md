---
kind: edge
routes:
  web: Web
steps:
- text: The Member chooses Submit week for approval
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: A time entry in the week is running
  kind: condition
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Running]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the submission and asks for the timer to be stopped
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
---

# Submitting a week with a running timer is refused

## Trigger

A person submits a week in which one of their timers is still running.

## Outcome

Nothing is submitted; the person is asked to stop the timer first.
