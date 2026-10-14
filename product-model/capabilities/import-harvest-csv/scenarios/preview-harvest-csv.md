---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses a Harvest CSV file and Preview file (dry-run)
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::importers
- text: The Product queues a preview import of the uploaded file
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: creates, to: Queued, facts: [Source, Mode, Scope, Counts, Record errors]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product starts the queued import
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Queued, to: Running, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product reads the file and reports what a commit would create, update, skip and fail, writing nothing
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Running, to: Completed, facts: [Counts, Record errors]}
  contexts:
    web:
      place: web::administration::importers
---

# Preview a Harvest CSV import

## Trigger

An admin chooses a Harvest CSV file and Preview file (dry-run).

## Outcome

A report shows what a real run would create, update, skip and fail, and nothing is written.
