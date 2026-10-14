---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager starts New project from a client page, with that client selected, and fills in the project
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: [Name, Currency]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::new-project
- text: The Product keeps the form as the Manager's private draft as it changes
  kind: product
  actor: manager
  entities:
  - {entity: project-draft, effect: creates, facts: [Settings, Saved at]}
  contexts:
    web:
      place: web::team::new-project
- text: The Manager adds tasks with their billing and access, and teammates with their project roles and rates
  kind: actor
  actor: manager
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::new-project
- text: The Manager chooses Save project
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::new-project
- text: The Product creates the active project with its tasks and team
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: creates, to: Active, facts: [Name, Code, Dates, Tags, Notes, Currency, Project type, Billing rates, Budget, Budget alert, Fees, Invoice defaults, Report visibility]}
  - {entity: project-task, effect: creates, to: Active, facts: [Billable, Hourly rate, Budget, Access, Selected people], with: project}
  - {entity: team-membership, effect: creates, facts: [Project role, Billable rate, Cost rate, Budget], with: project}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::new-project
- text: The Product discards the Manager's saved draft
  kind: product
  actor: manager
  entities:
  - {entity: project-draft, effect: removes}
  contexts:
    web:
      place: web::team::new-project
---

# Create a project for a client

## Trigger

A manager chooses New project from a client's page.

## Outcome

The project is created for that client.
