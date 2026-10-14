---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager selects projects, chooses Archive projects and confirms
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
- text: The Product archives every selected project
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: changes, from: Active, to: Archived, facts: []}
  contexts:
    web:
      place: web::team::projects
---

# Archive several projects at once

## Trigger

A manager selects up to 100 projects and chooses Archive projects, then confirms.

## Outcome

Every selected project is archived together, or none is.
