---
kind: edge
routes:
  web: Web
steps:
- text: The Admin picks a lower role for an active account holding the Admin role
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
- text: The Product refuses the change
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::user-management
---

# Demoting the last active admin is refused

## Trigger

An admin picks a non-admin role for the organization's only active admin, including themselves.

## Outcome

The role stays Admin and the admin is told the organization must keep an active admin.
