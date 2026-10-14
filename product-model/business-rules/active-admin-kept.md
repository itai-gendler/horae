---
appliesTo:
- type: capability
  id: change-user-role
- type: capability
  id: deactivate-user
- type: entity
  id: account
  facts:
  - Role
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#ensure_other_active_admin
---

# The organization always keeps an active admin

Demoting or deactivating the last active admin, oneself included, is refused.
