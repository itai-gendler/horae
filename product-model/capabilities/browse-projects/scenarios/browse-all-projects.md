---
kind: primary
routes:
  web: Web
steps:
- text: The Manager opens Projects and filters the list
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::projects
- text: The Product lists every matching project with its client, type, tags and budget progress
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name, Code, Project type, Tags, Budget progress]}
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
---

# Browse every project

## Trigger

A manager opens Projects and optionally filters by active, budgeted or archived, by client, by tag or by name.

## Outcome

The manager sees every matching project with its client, type and budget progress.
