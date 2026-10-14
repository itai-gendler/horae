---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager switches the filter to Approved or All
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::approvals
- text: The Product lists the matching weekly timesheets
  kind: product
  actor: manager
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: [Week, Submitted at, Total time, Billable time]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::approvals
---

# Show approved or all weeks

## Trigger

A manager switches the Approvals filter to Approved or All.

## Outcome

The list shows the approved weeks, or every submitted week.
