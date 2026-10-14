---
kind: alternative
routes:
  web: Web
steps:
- text: The Member opens Projects
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::projects
- text: The Product lists the projects the Member is on the team of or has tracked time on
  kind: product
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name, Code, Tags]}
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::projects
---

# Browse one's own projects

## Trigger

A member opens Projects.

## Outcome

The member sees only the projects they are on the team of or have tracked time on.

## Edge cases

- Budget progress shows only for projects whose report visibility includes everyone on the project, or where the person is a project manager.
