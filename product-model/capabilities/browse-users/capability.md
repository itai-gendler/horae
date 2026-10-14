---
domain: user-management
availability:
- {place: 'web::administration'}
- {place: admin-cli}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#list_users
- kind: code
  role: implementation
  target: crates/horae/src/pages/admin.rs#LegacyAdminUsers
- kind: code
  role: implementation
  target: crates/horae/src/cli.rs#UserAction
---

# Browse users

An admin, or the operator on the command line, lists the organization's accounts, deactivated ones included.
