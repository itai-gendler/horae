---
kind: primary
routes:
  web: Web
steps:
- text: The Admin picks a new role for an account
  kind: actor
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Name, Role]}
  contexts:
    web:
      place: web::administration::user-management
- text: The Product saves the account's new role
  kind: product
  actor: admin
  entities:
  - {entity: account, effect: changes, facts: [Role]}
  contexts:
    web:
      place: web::administration::user-management
---

# Change a person's role

## Trigger

An admin picks another role for a person on User Management.

## Outcome

The person holds the new role from their next action on.
