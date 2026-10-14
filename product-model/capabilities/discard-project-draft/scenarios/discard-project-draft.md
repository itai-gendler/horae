---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Discard draft
  kind: actor
  actor: manager
  entities:
  - {entity: project-draft, effect: reads, facts: [Saved at]}
  contexts:
    web:
      place: web::team::new-project
- text: The Product deletes the Manager's draft
  kind: product
  actor: manager
  entities:
  - {entity: project-draft, effect: removes}
  contexts:
    web:
      place: web::team::new-project
---

# Discard a project draft

## Trigger

A manager with a saved draft chooses Discard draft.

## Outcome

The draft is gone and New project starts empty next time.
