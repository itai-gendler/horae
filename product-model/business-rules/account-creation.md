---
appliesTo:
- type: entity
  id: account
  effect: creates
permits:
- actors:
  - admin
  - operator
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#create_user
- kind: code
  role: implementation
  target: crates/horae/src/cli.rs
---

# Only admins and the operator add people

Accounts are created by an admin in the web application or by the operator on the command line.
