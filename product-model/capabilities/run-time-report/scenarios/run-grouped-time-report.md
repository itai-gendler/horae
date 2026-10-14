---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses dates, a grouping by project, client, task or person, and optional client, project, teammate or tag filters
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: client, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::reports
- text: The Product totals every matching time entry of every person by group
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Duration, Rounded duration, Billable]}
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: client, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::reports
---

# Run a grouped time report

## Trigger

A manager opens Reports and chooses a period, a grouping and optional filters.

## Outcome

Each group shows its total, rounded and billable hours, with a grand total.

## Edge cases

- Unsubmitted time counts with its duration rounded on the fly by the organization's rule.
