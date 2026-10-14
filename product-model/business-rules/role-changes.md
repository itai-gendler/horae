---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts:
  - Role
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#set_user_role
---

# Only admins change a person's role

Roles are assigned by admins.
