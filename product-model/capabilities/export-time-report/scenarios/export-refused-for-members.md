---
kind: validation
routes:
  web: Web
steps:
- text: The Member requests a time export
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::reports
- text: The Product refuses the export
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::reports
---

# Exports are closed to members

## Trigger

A member requests a time export.

## Outcome

No file is produced.
