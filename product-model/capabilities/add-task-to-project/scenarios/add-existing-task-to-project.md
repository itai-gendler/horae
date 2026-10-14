---
kind: primary
routes:
  web: Web
steps:
- text: The Manager finds a task, sets whether it is billable here, its rate, budget and access, and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: task, effect: reads, facts: [Name, Archived]}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product offers the task on the project
  kind: product
  actor: manager
  entities:
  - {entity: project-task, effect: creates, to: Active, facts: [Billable, Hourly rate, Budget, Access, Selected people]}
  - {entity: project, effect: reads, facts: []}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Add an existing task to a project

## Trigger

A manager picks a task in the project's Tasks section and saves.

## Outcome

Everyone allowed can track time on the task in this project.
