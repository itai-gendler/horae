---
kind: primary
routes:
  api: Harvest API
steps:
- text: The Manager requests a page of users
  kind: actor
  actor: manager
  entities: []
  contexts:
    api:
      place: harvest-api
- text: The Product returns a page of people with their names, emails and roles
  kind: product
  actor: manager
  entities:
  - {entity: account, effect: reads, facts: [Name, Email, Role]}
  contexts:
    api:
      place: harvest-api
---

# List people through the API

## Trigger

An integration signed in as a manager requests users.

## Outcome

A page of the organization's people with their names, emails and roles is returned.
