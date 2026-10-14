---
kind: primary
routes:
  web: Web
steps:
- text: A project's spending reaches its budget alert threshold in the current period
  kind: condition
  unattended: true
  entities:
  - {entity: project, effect: reads, facts: [Budget, Budget alert, Budget progress]}
  - {entity: budget-alert, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project
- text: The Product records one budget alert for each admin, each manager, each of the project's project managers and its creator
  kind: product
  entities:
  - {entity: budget-alert, effect: creates, to: Pending, facts: [Threshold, Period, Recipient]}
  - {entity: manager, effect: reads, facts: []}
  - {entity: admin, effect: reads, facts: []}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project
- text: The Product hands each budget alert to the mail program
  kind: product
  entities:
  - {entity: budget-alert, effect: changes, from: Pending, to: Delivered, facts: []}
  contexts:
    web:
      place: web::team::project
---

# Send a budget alert

## Trigger

Tracked time or a new month brings a project with a budget alert to its threshold.

## Outcome

Each person following the project receives one email for that threshold and period.

## Edge cases

- Acceptance by the mail program is not proof of receipt.
