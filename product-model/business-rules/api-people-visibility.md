---
appliesTo:
- type: entity
  id: account
  effect: reads
  contexts:
  - {place: harvest-api}
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: has, entity: member}
references:
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#users_page
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#users_me
---

# Through the API, only managers and admins list people

Members reading people through the Harvest-style API get only their own profile.
