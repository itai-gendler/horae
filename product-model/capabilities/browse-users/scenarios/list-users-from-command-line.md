---
kind: alternative
routes:
  cli: Command line
steps:
- text: The Operator runs the user list command
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: admin-cli
- text: The Product prints every account with its email, name and role
  kind: product
  actor: operator
  entities:
  - {entity: account, effect: reads, facts: [Name, Email, Role]}
  contexts:
    cli:
      place: admin-cli
---

# List users from the command line

## Trigger

The operator runs `horae user list`.

## Outcome

The command prints every account.
