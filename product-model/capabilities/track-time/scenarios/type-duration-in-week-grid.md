---
kind: alternative
routes:
  web: Web
steps:
- text: The Member types a duration into an empty day cell of a row
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product records an open time entry for that day, project and task
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: creates, to: Open, facts: [Date, Project task, Duration, Billable, Running, Position]}
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::timesheet
---

# Type a duration into an empty week cell

## Trigger

A person types a duration into an empty day cell of a project task row in the week view.

## Outcome

A new open time entry for that day and project task appears and the totals update.
