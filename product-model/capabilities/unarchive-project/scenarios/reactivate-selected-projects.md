---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager selects archived projects, chooses Reactivate projects and confirms
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
- text: The Product reactivates every selected project
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: changes, from: Archived, to: Active, facts: []}
  contexts:
    web:
      place: web::team::projects
---

# Reactivate several projects at once

## Trigger

A manager selects archived projects and chooses Reactivate projects, then confirms.

## Outcome

Every selected project is active again.
