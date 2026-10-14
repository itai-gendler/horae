---
appliesTo:
- type: capability
  id: track-time
- type: capability
  id: start-timer
- type: capability
  id: edit-time-entry
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0034_task_tracking_access.sql
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#choices
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#eligible
---

# Time is tracked only on an active project task the person may use

New time needs an active client, project and task, a project task offered on the project, and a person on the project's team; admins may track on any active project without being on its team. A task restricted to named people takes time only from them.
