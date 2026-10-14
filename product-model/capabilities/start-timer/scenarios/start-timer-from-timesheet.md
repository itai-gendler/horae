---
kind: primary
routes:
  web: Web
steps:
- text: The Member picks a project and task and optional notes in today's new-entry dialog and chooses Start timer
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product records a running open time entry for today with no duration yet
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: creates, to: Open, facts: [Date, Project task, Duration, Notes, Billable, Running, Timer start, Position]}
  contexts:
    web:
      place: web::team::timesheet
---

# Start a timer from the timesheet

## Trigger

A person opens the new-entry dialog on today's column and leaves the duration empty.

## Outcome

A running time entry for today appears and counts up.
