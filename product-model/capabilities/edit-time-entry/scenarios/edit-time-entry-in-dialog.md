---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens an open time entry and changes its project and task, date, duration, start time or notes
  kind: actor
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Project task, Duration, Start time, Notes]}
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product saves the changes, keeping the entry billable only while its task is billable on its project
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Date, Project task, Duration, Start time, Notes, Billable]}
  - {entity: project, effect: reads, facts: [Project type]}
  - {entity: project-task, effect: reads, facts: [Billable]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
---

# Edit a time entry in its dialog

## Trigger

A person opens one of their open time entries.

## Outcome

The entry shows its new values and the totals follow.

## Edge cases

- Saving with nothing changed records no change.
- Moving the entry to another project task needs that project task to be one the person may currently track on.
