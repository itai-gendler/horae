---
kind: alternative
routes:
  api: Harvest API
steps:
- text: The Member requests their own profile
  kind: actor
  actor: member
  entities: []
  contexts:
    api:
      place: harvest-api
- text: The Product returns the Member's own name, email and role
  kind: product
  actor: member
  entities:
  - {entity: account, effect: reads, facts: [Name, Email, Role]}
  contexts:
    api:
      place: harvest-api
references:
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#users_me
---

# Read one's own profile through the API

## Trigger

An integration requests the current user.

## Outcome

The signed-in person's own name, email, role and status are returned.
