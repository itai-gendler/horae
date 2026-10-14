---
kind: validation
routes:
  cli: Command line
steps:
- text: The Operator runs the init command
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: admin-cli
- text: An organization already exists
  kind: condition
  actor: operator
  entities:
  - {entity: organization, effect: reads, facts: [Name]}
  contexts:
    cli:
      place: admin-cli
- text: The Product refuses and creates nothing
  kind: product
  actor: operator
  entities: []
  contexts:
    cli:
      place: admin-cli
---

# Initializing an installation that already has an organization is refused

## Trigger

The operator runs `horae init` where an organization already exists.

## Outcome

Nothing is created; the command names the existing organization and points to user create.
