---
appliesTo:
- type: entity
  id: account
  effect: changes
  to: Deactivated
- type: entity
  id: account
  effect: changes
  to: Active
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#set_user_active
---

# Only admins deactivate or reactivate a person

Whether a person may sign in is decided by admins.
