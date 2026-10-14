---
kind: alternative
routes:
  api: Harvest API
steps:
- text: The Member requests a page of client records
  kind: actor
  actor: member
  entities:
  - {entity: client, effect: reads, facts: []}
  contexts:
    api:
      place: harvest-api
- text: The Product returns a page of client records
  kind: product
  actor: member
  entities:
  - {entity: client, effect: reads, facts: [Name, Currency]}
  contexts:
    api:
      place: harvest-api
references:
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#list_clients
---

# List clients through the API

## Trigger

An integration signed in as a person requests clients, optionally only active or inactive ones.

## Outcome

A page of the organization's clients is returned.
