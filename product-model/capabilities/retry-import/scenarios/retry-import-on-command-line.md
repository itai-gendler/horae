---
kind: alternative
routes:
  cli: Command line
steps:
- text: The Admin runs the jobs retry command for a cancelled import
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    cli:
      place: admin-cli
- text: The Product queues the import again
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Cancelled, to: Queued, facts: []}
  contexts:
    cli:
      place: admin-cli
---

# Retry a cancelled import on the command line

## Trigger

An admin runs `horae jobs retry` for a cancelled import.

## Outcome

The import is queued again.
