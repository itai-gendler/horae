---
kind: alternative
routes:
  web: Web
steps:
- text: The Member chooses Export, a set of projects and a format
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::projects
- text: The Product produces a file of the matching projects whose budget progress the Member may see
  kind: product
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name, Code, Project type, Currency, Budget]}
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
---

# Export the projects one may follow

## Trigger

A member exports projects.

## Outcome

The file holds only the projects whose budget progress the member may see.
