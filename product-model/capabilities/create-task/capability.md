---
domain: user-management
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#create_task
- kind: code
  role: implementation
  target: crates/horae/src/pages/admin.rs#LegacyAdminUsers
---

# Create task

An admin adds a task the organization's projects can offer.
