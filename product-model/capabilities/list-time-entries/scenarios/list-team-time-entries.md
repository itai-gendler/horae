---
kind: alternative
routes:
  api: Harvest API
steps:
- text: The Manager requests a page of time entries, optionally for one person
  kind: actor
  actor: manager
  entities: []
  contexts:
    api:
      place: harvest-api
- text: The Product returns a page of everyone's matching time entries
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Project task, Duration, Rounded duration, Notes, Billable, Running, Timer start]}
  contexts:
    api:
      place: harvest-api
---

# List the team's time entries

## Trigger

An integration signed in as a manager requests time entries, optionally for one person.

## Outcome

A page of the organization's entries, or of that person's, is returned.
