---
kind: edge
routes:
  web: Web
steps:
- text: The Member saves time on a project and task chosen earlier
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::timesheet
- text: The project, its client or the task is archived or inactive, the Member is off the project's team, or the task is limited to other people
  kind: condition
  actor: member
  entities:
  - {entity: project, effect: reads, facts: []}
  - {entity: client, effect: reads, facts: []}
  - {entity: task, effect: reads, facts: [Archived]}
  - {entity: project-task, effect: reads, facts: [Access, Selected people]}
  - {entity: team-membership, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the entry and adds nothing
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#eligible
- kind: code
  role: implementation
  target: crates/horae/migrations/0034_task_tracking_access.sql
---

# Adding time on a project and task that is no longer available is refused

## Trigger

A person saves time on a project and task that became unavailable to them after the choices loaded.

## Outcome

No time entry is added; the timesheet asks the person to refresh.
