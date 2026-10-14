---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager chooses Everyone on the project for a task and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product opens the task to the whole team
  kind: product
  actor: manager
  entities:
  - {entity: project-task, effect: changes, facts: [Access, Selected people]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Open a task to everyone on the project

## Trigger

A manager sets a limited task back to everyone on the project and saves.

## Outcome

Everyone on the team can track on the task again.
