---
kind: alternative
routes:
  cli: Command line
steps:
- text: The Operator runs the user create command with an email, a name and a role
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: admin-cli
- text: The Product creates an active account with that email, name and role
  kind: product
  actor: operator
  entities:
  - {entity: account, effect: creates, to: Active, facts: [Name, Email, Role]}
  contexts:
    cli:
      place: admin-cli
---

# Create a user from the command line

## Trigger

The operator runs `horae user create` with an email, a name and a role.

## Outcome

The person has an active account with that role.
