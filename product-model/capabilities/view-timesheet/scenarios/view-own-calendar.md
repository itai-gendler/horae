---
kind: alternative
routes:
  web: Web
steps:
- text: The Member opens the calendar view and picks a span
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product places each timed entry at its start time and stacks untimed entries by position
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Start time, Duration, Position, Project task]}
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::timesheet
---

# View one's own calendar

## Trigger

A signed-in person switches the timesheet to the calendar view for a day, five days or a week.

## Outcome

Timed entries sit at their start time and untimed entries stack at the top of their day in their saved order.
