---
kind: primary
routes:
  web: Web
steps:
- text: The Manager changes the project's settings and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: &id001 [Name, Code, Dates, Tags, Notes, Currency, Project type, Billing rates, Budget, Budget alert, Fees, Invoice defaults, Report visibility]}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product saves the project's new settings
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: changes, facts: *id001}
  contexts:
    web:
      place: web::team::project-settings
---

# Edit a project

## Trigger

A manager chooses Edit project and changes its settings.

## Outcome

The project keeps the new settings.

## Edge cases

- Leaving with unsaved changes asks whether to keep editing or discard them.
