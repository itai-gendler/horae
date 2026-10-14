---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager chooses New client in the project form and enters its name, currency and optional default rate
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: []}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::new-project
- text: The Product creates the active client record and selects it for the project
  kind: product
  actor: manager
  entities:
  - {entity: client, effect: creates, to: Active, facts: [Name, Currency, Default rate]}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::new-project
---

# Create a client while setting up a project

## Trigger

A manager setting up a new project chooses New client in the client picker.

## Outcome

The new client is created and selected for the project being set up.
