---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens User Management
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::user-management
- text: The Product lists every account, active or deactivated
  kind: product
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Name, Email, Role]}
  contexts:
    web:
      place: web::administration::user-management
---

# Browse users

## Trigger

An admin opens User Management.

## Outcome

The admin sees every account with its name, email, role and whether it is active.
