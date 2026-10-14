---
appliesTo:
- type: entity
  id: team-membership
  effect: changes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/editing/associations.rs
---

# Only managers and admins change a teammate's project role or rates

Project roles and per-project rates are set by managers and admins.
