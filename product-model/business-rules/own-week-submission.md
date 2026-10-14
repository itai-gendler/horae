---
appliesTo:
- type: entity
  id: time-entry
  effect: changes
  to: Submitted
permits:
- related:
  - {verb: owns, entity: member}
- related:
  - {verb: owns, entity: manager}
- related:
  - {verb: owns, entity: admin}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#submit_week
---

# People submit only their own time

Submitting a week moves the submitter's own open time to Submitted.
