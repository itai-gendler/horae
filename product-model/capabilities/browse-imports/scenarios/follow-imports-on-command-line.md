---
kind: alternative
routes:
  cli: Command line
steps:
- text: The Admin runs a jobs command with a saved session
  kind: actor
  actor: admin
  entities: []
  contexts:
    cli:
      place: admin-cli
- text: The Product prints the requested import details
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: [Source, Mode, Counts, Record errors]}
  contexts:
    cli:
      place: admin-cli
---

# Follow imports on the command line

## Trigger

An admin runs `horae jobs list`, `status`, `report`, `errors` or `wait`.

## Outcome

The command prints the imports, one import's state or report, or its record errors.
