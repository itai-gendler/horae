---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Activate on a deactivated account
  kind: actor
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::administration::user-management
- text: The Product reactivates the account
  kind: product
  actor: admin
  entities:
  - {entity: account, effect: changes, from: Deactivated, to: Active, facts: []}
  contexts:
    web:
      place: web::administration::user-management
---

# Activate a person

## Trigger

An admin chooses Activate on a deactivated account.

## Outcome

The person can sign in again with their previous role and time.
