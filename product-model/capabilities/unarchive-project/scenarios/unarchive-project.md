---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Unarchive on an archived project
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
- text: The Product reactivates the project
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: changes, from: Archived, to: Active, facts: []}
  contexts:
    web:
      place: web::team::projects
---

# Unarchive a project

## Trigger

A manager chooses Unarchive on an archived project.

## Outcome

The project is active and takes time again.
