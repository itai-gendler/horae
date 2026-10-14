---
kind: primary
routes:
  web: Web
steps:
- text: The Manager removes a teammate and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product takes the person off the project's team
  kind: product
  actor: manager
  entities:
  - {entity: team-membership, effect: removes}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Remove a teammate from a project

## Trigger

A manager removes a person from a project's team and saves.

## Outcome

The person can no longer track new time on the project; the time they tracked stays.
