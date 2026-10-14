---
domain: projects
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project/tasks.rs
- kind: code
  role: implementation
  target: crates/horae/migrations/0034_task_tracking_access.sql
---

# Change project task access

A manager or admin decides whether everyone on a project or only selected people may track on one of its tasks.
