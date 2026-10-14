---
appliesTo:
- type: entity
  id: team-membership
  effect: reads
  facts:
  - Billable rate
  - Cost rate
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/editing/protected.rs
---

# Only managers and admins see teammates' project rates

Per-project billable and cost rates are shown only to managers and admins.
