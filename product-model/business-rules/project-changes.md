---
appliesTo:
- type: entity
  id: project
  effect: changes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/editing.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#set_project_active
---

# Only managers and admins change, archive or unarchive a project

Project settings and whether a project is active are reserved to managers and admins.
