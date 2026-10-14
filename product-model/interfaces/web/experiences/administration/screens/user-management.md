---
entities:
- entity: account
  shows:
  - Name
  - Email
  - Role
  collects:
  - Name
  - Email
  - Role
- entity: task
  shows:
  - Name
  - Billable by default
  - Archived
  collects:
  - Name
  - Billable by default
entryPoints:
- web: /admin/users
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/admin.rs#LegacyAdminUsers
---

# User Management

Every account in the organization, active or deactivated, with its role, and the
organization's tasks.
