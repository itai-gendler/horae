---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Deactivate on an active account
  kind: actor
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::administration::user-management
- text: The Product deactivates the account
  kind: product
  actor: admin
  entities:
  - {entity: account, effect: changes, from: Active, to: Deactivated, facts: []}
  contexts:
    web:
      place: web::administration::user-management
---

# Deactivate a person

## Trigger

An admin chooses Deactivate on an active account.

## Outcome

The person can no longer sign in or track time; their time stays in reports and invoices.
