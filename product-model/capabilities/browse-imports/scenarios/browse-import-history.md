---
kind: primary
routes:
  web: Web
steps:
- text: The Admin selects an import in the history
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product shows the import's source, mode, scope, counts and record errors
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: [Source, Mode, Scope, Counts, Record errors]}
  contexts:
    web:
      place: web::administration::importers
---

# Browse the import history

## Trigger

An admin opens Importers and selects an import from the history.

## Outcome

The admin sees its source, mode, progress and counts, and can download every record error.
