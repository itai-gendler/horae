---
kind: alternative
routes:
  cli: Command line
steps:
- text: The Admin runs the jobs cancel command for a queued import
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    cli:
      place: admin-cli
- text: The Product cancels the import
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Queued, to: Cancelled, facts: []}
  contexts:
    cli:
      place: admin-cli
---

# Cancel an import on the command line

## Trigger

An admin runs `horae jobs cancel`.

## Outcome

The import is cancelled.
