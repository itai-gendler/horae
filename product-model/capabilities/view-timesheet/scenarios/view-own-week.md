---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens the timesheet's week view
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product shows the Member's own time entries for the week with their project, task and client
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Project task, Duration, Notes, Billable, Running]}
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product totals each day and the week from the entries' durations
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Duration]}
  contexts:
    web:
      place: web::team::timesheet
---

# View one's own week

## Trigger

A signed-in person opens the timesheet, which shows the current week by default.

## Outcome

The person sees each of their entries for the week with its project, task and client, each day's total, the week's total, and whether the week is submitted.

## Edge cases

- When the week holds time but none of it is open, it shows as Submitted instead of offering submission.
