---
kind: primary
routes:
  web: Web
steps:
- text: The Manager picks a client and enters the project's name, code, dates, tags, notes, type, billing rates, budget, fees, payment terms and taxes
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

# Create a project

## Trigger

A manager chooses New project.

## Outcome

The project is active with its tasks and team, and people on its team can track time on it.

## Edge cases

- Dates are advisory and never stop anyone tracking time.
- When no mail program is configured for budget alerts, the budget alert option is unavailable and says why.
- The code suggestion shows the last code used.
