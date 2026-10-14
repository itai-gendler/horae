---
appliesTo:
- type: capability
  id: initialize-organization
- type: entity
  id: organization
references:
- kind: code
  role: implementation
  target: crates/horae/src/init.rs#run
---

# An installation holds exactly one organization

Initialization refuses to create a second organization; further people are added to the existing one.
