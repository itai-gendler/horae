---
appliesTo:
- type: capability
  id: archive-project
- type: capability
  id: archive-project-task
- type: capability
  id: deactivate-client
- type: capability
  id: remove-teammate-from-project
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#set_project_active
- kind: code
  role: implementation
  target: crates/horae/migrations/0034_task_tracking_access.sql
---

# Archiving or deactivating stops new time and keeps tracked time

An archived project, an archived project task and an inactive client take no new time; time already tracked on them stays in timesheets, reports and invoices.
