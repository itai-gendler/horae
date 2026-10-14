---
appliesTo:
- type: entity
  id: team-membership
  effect: removes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/editing/associations.rs
---

# Only managers and admins take people off a project's team

Team memberships are removed by managers and admins.
