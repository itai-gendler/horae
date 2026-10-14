---
appliesTo:
- type: entity
  id: project-task
  effect: creates
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/editing/catalog.rs
---

# Only managers and admins offer tasks on projects

Project tasks are added by managers and admins, in the project form or through imports.
