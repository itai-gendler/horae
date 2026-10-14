---
kind: primary
routes:
  web: Web
steps:
- text: The Manager opens a project
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project
- text: The Product shows the project's details, tasks, team, budget progress and fee balances
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Name, Code, Dates, Tags, Notes, Currency, Budget progress, Fee balance]}
  - {entity: client, effect: reads, facts: [Name]}
  - {entity: project-task, effect: reads, facts: [Billable]}
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: team-membership, effect: reads, facts: [Project role]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::project
---

# View a project

## Trigger

A manager opens a project.

## Outcome

The manager sees its details and notes, its tasks, its team with their project roles, its budget progress and its fee balances.
