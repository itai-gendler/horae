---
kind: primary
routes:
  web: Web
steps:
- text: The Manager archives a task in the project's Tasks section and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product archives the task on this project
  kind: product
  actor: manager
  entities:
  - {entity: project-task, effect: changes, from: Active, to: Archived, facts: []}
  - {entity: project, effect: reads, facts: []}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Archive a task on a project

## Trigger

A manager archives one of a project's tasks and saves.

## Outcome

The task takes no new time on this project; time already tracked on it stays.
