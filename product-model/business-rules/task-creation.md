---
appliesTo:
- type: entity
  id: task
  effect: creates
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#create_task
---

# Only managers and admins create tasks

Tasks are created by managers and admins, in User Management, in the project form or through imports.
