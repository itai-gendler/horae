---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Commit this import for the uploaded file
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product queues a committing import of the uploaded file
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: creates, to: Queued, facts: [Source, Mode, Scope, Counts, Record errors]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product starts the queued import
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Queued, to: Running, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product creates the client records not yet in Horae
  kind: product
  actor: admin
  entities:
  - {entity: client, effect: creates, to: Active, facts: [Name, Currency, Default rate]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product creates the project records not yet in Horae
  kind: product
  actor: admin
  entities:
  - {entity: project, effect: creates, to: Active, facts: [Name, Code, Project type, Currency, Budget]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product creates the task records not yet in Horae and offers them on their projects
  kind: product
  actor: admin
  entities:
  - {entity: task, effect: creates, facts: [Name, Billable by default, Archived]}
  - {entity: project-task, effect: creates, to: Active, facts: [Billable, Hourly rate], with: task}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product creates the people's time entries as open time
  kind: product
  actor: admin
  entities:
  - {entity: time-entry, effect: creates, to: Open, facts: [Date, Project task, Duration, Notes, Billable]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product completes the import and reports created, updated, skipped and errored records
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Running, to: Completed, facts: [Counts, Record errors]}
  contexts:
    web:
      place: web::administration::importers
---

# Commit a Harvest CSV import

## Trigger

An admin who reviewed a CSV preview chooses Commit this import.

## Outcome

The file's records exist in Horae and the report shows what was created, updated and skipped.
