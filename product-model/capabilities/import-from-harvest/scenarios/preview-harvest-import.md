---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Preview import (dry-run), for everything or only changes since the last run
  kind: actor
  actor: admin
  entities:
  - {entity: harvest-connection, effect: reads, facts: [Harvest account]}
  - {entity: import, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product queues a preview import from the Harvest connection
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: creates, to: Queued, facts: [Source, Mode, Scope, Counts, Record errors]}
  - {entity: harvest-connection, effect: reads, facts: []}
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
- text: The Product reads Harvest and reports what a commit would create, update, skip and fail, writing nothing
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Running, to: Completed, facts: [Counts, Record errors]}
  contexts:
    web:
      place: web::administration::importers
---

# Preview an import from Harvest

## Trigger

An admin with a Harvest connection chooses Preview import (dry-run).

## Outcome

A report shows what a real run would create, update, skip and fail, and nothing is written.

## Edge cases

- Leaving the page does not stop the import.
