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
- entity: project-draft
  verb: drafts
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: crates/core/src/types.rs
- kind: code
  role: implementation
  target: crates/core/src/state.rs#can_transition
---

# Admin

A person with every Manager ability who also manages the organization's people and their roles, connects Horae to Harvest and runs imports, and may track time on any active project without being on its team.
