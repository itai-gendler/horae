---
appliesTo:
- type: capability
  id: submit-timesheet
- type: capability
  id: generate-invoice
- type: entity
  id: time-entry
  facts:
  - Rounded duration
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#submit_user_week
- kind: code
  role: implementation
  target: crates/core/src/rounding.rs#effective_minutes
---

# Submitted and invoiced time keeps the rounded duration frozen when it was locked

Submitting a week or invoicing time freezes each entry's rounded duration by the organization's rounding increment and direction; reopening a week or voiding an invoice clears it again. Open time is rounded on the fly wherever it is reported.
