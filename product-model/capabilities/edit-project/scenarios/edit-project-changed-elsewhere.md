---
kind: edge
routes:
  web: Web
steps:
- text: The Manager chooses Save changes
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::project-settings
- text: The project was saved by someone else since the Manager opened it
  kind: condition
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product refuses the save and offers to reload the project
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Saving a project someone else changed meanwhile

## Trigger

A manager saves project settings after another person saved the same project.

## Outcome

Nothing is saved; the manager is asked to reload the project.
