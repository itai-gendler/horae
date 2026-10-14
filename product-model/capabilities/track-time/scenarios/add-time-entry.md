---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens the new-entry dialog for a day
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product offers only the projects and tasks the Member may currently track on
  kind: product
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name, Archived]}
  - {entity: project-task, effect: reads, facts: [Access, Selected people]}
  - {entity: team-membership, effect: reads, facts: []}
  - {entity: client, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The Member picks a project and task and enters a duration, an optional start time and notes
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product records an open time entry for the Member, billable only when the task is billable on that project
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: creates, to: Open, facts: [Date, Project task, Duration, Start time, Notes, Billable, Running, Position]}
  - {entity: project, effect: reads, facts: [Project type]}
  - {entity: project-task, effect: reads, facts: [Billable]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
---

# Add a time entry

## Trigger

A person opens the new-entry dialog for a day on their timesheet.

## Outcome

A new open time entry with the chosen project task, duration and notes appears on that day and in the totals.

## Edge cases

- A start time snaps to the 15-minute grid and the duration is shortened so the entry ends by midnight.
- Time on a non-billable project is recorded as non-billable whatever the person chose.
