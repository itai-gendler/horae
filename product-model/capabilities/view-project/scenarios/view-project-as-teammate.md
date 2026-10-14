---
kind: alternative
routes:
  web: Web
steps:
- text: The Member opens a project they are on the team of
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project
- text: The Product shows the project's details, tasks and team
  kind: product
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name, Code, Dates, Tags]}
  - {entity: client, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::project
---

# View a project as one of its team

## Trigger

A member on a project's team opens it.

## Outcome

The member sees its details, tasks and team; budget progress appears only when the project's report visibility allows it.
