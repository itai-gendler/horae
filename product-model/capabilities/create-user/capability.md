---
domain: user-management
availability:
- {place: 'web::administration'}
- {place: admin-cli}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#create_user
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#insert_user
- kind: code
  role: implementation
  target: crates/horae/src/cli.rs#UserAction
---

# Create user

An admin, or the operator on the command line, adds a person to the organization with a role.
