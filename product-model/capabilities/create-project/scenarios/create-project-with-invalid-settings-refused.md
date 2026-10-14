---
kind: validation
routes:
  web: Web
steps:
- text: The Manager chooses Save project with a required setting missing or invalid
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::new-project
- text: The Product creates nothing and points at the setting to correct
  kind: product
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::new-project
---

# Saving a project with invalid settings is refused

## Trigger

A manager saves a new project without a client or name, or with an invalid amount.

## Outcome

No project is created; the form points at the setting to correct and the draft is kept.
