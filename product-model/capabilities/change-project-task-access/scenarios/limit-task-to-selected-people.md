---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Only selected people for a task, picks people from the team, applies access and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product saves who may track on the task
  kind: product
  actor: manager
  entities:
  - {entity: project-task, effect: changes, facts: [Access, Selected people]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Limit a task to selected people

## Trigger

A manager sets a project task's access to only selected people, picks them and saves.

## Outcome

Only the selected people can track on the task in this project.

## Edge cases

- With nobody selected, nobody can track on the task.
