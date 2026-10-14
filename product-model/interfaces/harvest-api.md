---
type: api
actors:
- member
- manager
- admin
entryPoints:
- api: /harvest/v2/time_entries
- api: /harvest/v2/users/me
references:
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#router
- kind: spec
  role: intent
  target: specs/001-time-tracking-invoicing/contracts/harvest-api.md
---

# Harvest-style API

A read-only subset of the Harvest API v2 shape under `/harvest/v2`, authenticated with the
signed-in person's session, for integrations that read time, projects, clients, tasks and
people.
