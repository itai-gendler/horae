---
kind: primary
routes:
  api: Harvest API
steps:
- text: The Member requests a page of project records
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: []}
  contexts:
    api:
      place: harvest-api
- text: The Product returns a page of the project records the Member may follow
  kind: product
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name, Code, Project type, Currency, Budget]}
  contexts:
    api:
      place: harvest-api
---

# List projects through the API

## Trigger

An integration requests projects, optionally active or inactive only.

## Outcome

A page of the projects the person may follow is returned.
