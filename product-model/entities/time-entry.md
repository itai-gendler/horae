---
domain: timesheet
references:
- kind: code
  role: implementation
  target: crates/horae/src/models/time_entry.rs#TimeEntry
- kind: code
  role: implementation
  target: crates/core/src/state.rs#can_transition
- kind: code
  role: implementation
  target: crates/horae/migrations/0001_init.sql
---

# Time entry

Time one person spent on one project task on one day, typed as a duration or recorded by a
running timer.

## Information kept

- **Date** — the day the time was spent
- **Project task** — the project and task the time is tracked on
- **Duration** — the time spent, in whole minutes
- **Start time** — the time of day the work started, on a 15-minute grid; absent for untimed entries
- **Notes** — what the time was spent on
- **Billable** — whether the time can be billed to the client
- **Running** — whether a timer is still counting this entry
- **Timer start** — the moment a running timer started
- **Position** — the entry's place among the day's untimed entries
- **Rounded duration** — the duration rounded by the organization's rounding rule, frozen when the entry is submitted or invoiced

## States

### Open

The entry can be changed or deleted by the person who tracked it.

### Submitted

The entry's week has been submitted for approval; it is locked.

### Approved

The entry's week has been approved; it is locked and ready to invoice.

### Invoiced

The entry is billed on an invoice; it is locked.
