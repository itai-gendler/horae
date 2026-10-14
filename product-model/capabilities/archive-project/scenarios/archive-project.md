---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Archive on an active project
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
- text: The Product archives the project
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: changes, from: Active, to: Archived, facts: []}
  contexts:
    web:
      place: web::team::projects
---

# Archive a project

## Trigger

A manager chooses Archive on an active project.

## Outcome

The project is archived; it takes no new time and its tracked time stays.
