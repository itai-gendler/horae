---
kind: person
acts: external
relations:
- entity: account
  verb: has
  cardinality: one-to-one
- entity: time-entry
  verb: owns
  cardinality: one-to-many
- entity: weekly-timesheet
  verb: submits
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/core/src/types.rs
- kind: code
  role: implementation
  target: crates/core/src/state.rs#can_transition
---

# Member

A person who tracks their own time and submits their own weeks for approval. Member is the role every account starts with.
