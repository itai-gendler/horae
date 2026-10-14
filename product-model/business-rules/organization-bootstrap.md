---
appliesTo:
- type: entity
  id: organization
  effect: creates
permits:
- actors:
  - operator
references:
- kind: code
  role: implementation
  target: crates/horae/src/init.rs#run
---

# Only the operator creates the organization

The organization is created once, on the command line, by the operator.
