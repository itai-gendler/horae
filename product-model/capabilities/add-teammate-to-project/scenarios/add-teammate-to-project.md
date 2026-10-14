---
kind: primary
routes:
  web: Web
steps:
- text: The Manager adds a teammate, with a project role and optional rates and budget, and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product puts the person on the project's team
  kind: product
  actor: manager
  entities:
  - {entity: team-membership, effect: creates, facts: [Project role, Billable rate, Cost rate, Budget]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Add a teammate to a project

## Trigger

A manager adds a person to a project's team in its settings and saves.

## Outcome

The person is on the team and can track time on the project's open tasks.

## Edge cases

- Add everyone puts every active person on the team at once.
