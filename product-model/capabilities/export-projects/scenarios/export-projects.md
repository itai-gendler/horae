---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Export, a set of projects and a format
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::projects
- text: The Product produces a file of the matching projects
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name, Code, Project type, Currency, Budget]}
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
---

# Export projects

## Trigger

A manager chooses Export on Projects, picks active, budgeted or archived projects and CSV or Excel.

## Outcome

A file lists each project's client, code, name, type, currency, budget and status.
