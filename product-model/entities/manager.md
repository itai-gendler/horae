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

# Manager

A person who tracks their own time and also approves and reopens submitted weeks, manages clients and projects, reports on the organization's time and invoices clients.
