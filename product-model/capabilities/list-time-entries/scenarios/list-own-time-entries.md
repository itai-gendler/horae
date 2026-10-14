---
kind: primary
routes:
  api: Harvest API
steps:
- text: The Member requests a page of time entries
  kind: actor
  actor: member
  entities: []
  contexts:
    api:
      place: harvest-api
- text: The Product returns a page of the Member's own time entries
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Project task, Duration, Rounded duration, Notes, Billable, Running, Timer start]}
  contexts:
    api:
      place: harvest-api
---

# List one's own time entries

## Trigger

An integration signed in as a member requests time entries, optionally narrowed by dates, project or whether a timer is running.

## Outcome

A page of the member's own entries is returned, with links to further pages that keep the filters.

## Edge cases

- A page number below one, a page size outside 1 to 100 or an overflowing offset is refused as a bad request.
