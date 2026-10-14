---
kind: edge
routes:
  web: Web
steps:
- text: A budget alert has used its five delivery attempts or its recipient is no longer eligible
  kind: condition
  unattended: true
  entities:
  - {entity: budget-alert, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project
- text: The Product marks the budget alert failed
  kind: product
  entities:
  - {entity: budget-alert, effect: changes, from: Pending, to: Failed, facts: []}
  contexts:
    web:
      place: web::team::project
---

# A budget alert cannot be delivered

## Trigger

The mail program keeps refusing a budget alert, or its recipient is no longer eligible.

## Outcome

The budget alert stops as failed and is not retried further.
