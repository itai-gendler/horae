---
appliesTo:
- type: capability
  id: track-time
- type: capability
  id: edit-time-entry
- type: capability
  id: delete-time-entry
- type: capability
  id: reschedule-time-entry
- type: capability
  id: reorder-untimed-entries
- type: capability
  id: start-timer
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#apply
- kind: code
  role: implementation
  target: crates/core/src/state.rs#can_transition
---

# Time changes only while open and outside a submitted or approved week

Adding, changing, moving or deleting time is refused for an entry that is submitted, approved or invoiced, and for any day inside one of the person's submitted or approved weeks.

## Rationale

Submitted time carries frozen rounded durations that approvals and invoices rely on; changing it underneath them would put time on the books that billing never sees.
