---
appliesTo:
- type: capability
  id: submit-timesheet
- type: entity
  id: organization
  facts:
  - First day of the week
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#submit_user_week
---

# A submitted week starts on the organization's first day of the week

A week is submitted from the organization's first weekday through the sixth day after it; any other starting day is refused.
