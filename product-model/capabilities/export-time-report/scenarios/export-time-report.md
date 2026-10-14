---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Export CSV or Export XLSX
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::reports
- text: The Product produces a file of every matching time entry with the report's filters
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Duration, Rounded duration, Billable, Notes]}
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::reports
---

# Export the report's time

## Trigger

A manager chooses Export CSV or Export XLSX on Reports.

## Outcome

A file with each matching entry's date, project, task, person, hours, rounded hours, billable flag and notes downloads.
