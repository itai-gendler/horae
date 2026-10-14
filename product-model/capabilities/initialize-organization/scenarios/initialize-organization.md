---
kind: primary
routes:
  cli: Command line
steps:
- text: The Operator runs the init command with a name for the installation and the first administrator's email and name
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: admin-cli
- text: The Product creates the organization with default week and rounding settings and its first active account, holding the administrator role
  kind: product
  actor: operator
  entities:
  - {entity: organization, effect: creates, facts: [Name, First day of the week, Rounding increment, Rounding direction, Default currency, Long timer limit]}
  - {entity: account, effect: creates, to: Active, facts: [Name, Email, Role], with: organization}
  contexts:
    cli:
      place: admin-cli
---

# Initialize the organization

## Trigger

The operator runs `horae init` with an organization name and the first admin's email and name on an empty installation.

## Outcome

The installation has its organization with default settings and one active admin who can sign in.
