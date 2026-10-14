---
appliesTo:
- type: entity
  id: team-membership
  effect: creates
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/editing/associations.rs
---

# Only managers and admins put people on a project's team

Team memberships are created by managers and admins.
