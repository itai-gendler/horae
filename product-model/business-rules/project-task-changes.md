---
appliesTo:
- type: entity
  id: project-task
  effect: changes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/editing/task_activity.rs
---

# Only managers and admins change, archive or restore a project task

Billing, access and activity of a project task are set by managers and admins.
