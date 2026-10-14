---
kind: primary
routes:
  api: Harvest API
steps:
- text: The Member requests a page of task records
  kind: actor
  actor: member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    api:
      place: harvest-api
- text: The Product returns a page of task records
  kind: product
  actor: member
  entities:
  - {entity: task, effect: reads, facts: [Name, Billable by default, Archived]}
  contexts:
    api:
      place: harvest-api
---

# List tasks through the API

## Trigger

An integration requests tasks.

## Outcome

A page of the tasks the person may see is returned.
