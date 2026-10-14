---
kind: primary
routes:
  web: Web
steps:
- text: The Manager opens Approvals
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::approvals
- text: The Product lists every weekly timesheet awaiting approval with its teammate, total time and submission time
  kind: product
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: [Week, Submitted at, Total time, Billable time]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::approvals
---

# Browse weeks awaiting approval

## Trigger

A manager opens Approvals, which shows pending weeks first.

## Outcome

The manager sees each pending week with the teammate, hours and submission time, and the billable and non-billable split across them.
