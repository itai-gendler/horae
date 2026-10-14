---
kind: alternative
routes:
  cli: Command line
steps:
- text: The Admin runs the Harvest CSV import command with a file of at most 50 MiB
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    cli:
      place: admin-cli
- text: The Product queues the import of the uploaded file
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: creates, to: Queued, facts: [Source, Mode, Scope, Counts, Record errors]}
  contexts:
    cli:
      place: admin-cli
- text: The Product starts the queued import
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Queued, to: Running, facts: []}
  contexts:
    cli:
      place: admin-cli
- text: The Product runs the import and the command prints its outcome
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Running, to: Completed, facts: [Counts, Record errors]}
  contexts:
    cli:
      place: admin-cli
---

# Import a Harvest CSV on the command line

## Trigger

An admin runs `horae import harvest-csv FILE` with a saved session.

## Outcome

The command uploads the file and reports the queued import.
