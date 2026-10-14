---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Restore on a task archived on this project and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: task, effect: reads, facts: [Name, Archived]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product restores the task on this project
  kind: product
  actor: manager
  entities:
  - {entity: project-task, effect: changes, from: Archived, to: Active, facts: []}
  - {entity: project, effect: reads, facts: []}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Restore a task on a project

## Trigger

A manager chooses Restore on a task archived on the project and saves.

## Outcome

The task takes time on this project again.

## Edge cases

- A task archived in the organization's task catalog must be restored there first.
