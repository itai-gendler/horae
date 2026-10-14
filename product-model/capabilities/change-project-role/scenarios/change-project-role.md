---
kind: primary
routes:
  web: Web
steps:
- text: The Manager picks a new project role for a teammate and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: team-membership, effect: reads, facts: [Project role]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product saves the teammate's new project role
  kind: product
  actor: manager
  entities:
  - {entity: team-membership, effect: changes, facts: [Project role]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Change a teammate's project role

## Trigger

A manager changes a teammate's role on a project and saves.

## Outcome

The teammate holds the new project role.
