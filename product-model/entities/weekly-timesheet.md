---
domain: approvals
references:
- kind: code
  role: implementation
  target: crates/horae/src/models/approval.rs#Approval
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs
---

# Weekly timesheet

One person's week of time, submitted for approval. It exists from submission until a
manager or admin reopens it.

## Information kept

- **Week** — the first and last day of the submitted week
- **Submitted at** — when the person last submitted the week
- **Approved by** — who approved the week
- **Approved at** — when the week was approved
- **Total time** — the sum of the person's tracked time in the week
- **Billable time** — the billable part of that total

## States

### Awaiting approval

The week is submitted and waits for a decision.

### Approved

A manager or admin approved the week.
