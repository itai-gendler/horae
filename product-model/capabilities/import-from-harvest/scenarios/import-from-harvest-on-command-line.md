---
kind: alternative
routes:
  cli: Command line
steps:
- text: The Admin runs the Harvest API import command with a saved session
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    cli:
      place: admin-cli
- text: The Product queues the import from the Harvest connection
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: creates, to: Queued, facts: [Source, Mode, Scope, Counts, Record errors]}
  - {entity: harvest-connection, effect: reads, facts: []}
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
references:
- kind: code
  role: implementation
  target: crates/horae/src/cli/imports.rs
- kind: spec
  role: intent
  target: specs/006-harvest-jobs-cli/contracts/cli.md
---

# Import from Harvest on the command line

## Trigger

An admin runs `horae import harvest-api` with a saved session, as a preview or a commit.

## Outcome

The command reports the queued import and, when asked to wait, its outcome.
