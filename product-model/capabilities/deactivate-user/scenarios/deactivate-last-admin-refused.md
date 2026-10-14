---
kind: edge
routes:
  web: Web
steps:
- text: The Admin chooses Deactivate on an active account holding the Admin role
  kind: actor
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Role]}
  contexts:
    web:
      place: web::administration::user-management
- text: No other active account has the Admin role
  kind: condition
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Role]}
  contexts:
    web:
      place: web::administration::user-management
- text: The Product refuses the deactivation
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::user-management
---

# Deactivating the last active admin is refused

## Trigger

An admin deactivates the organization's only active admin, including themselves.

## Outcome

The account stays active.
