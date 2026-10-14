---
entities:
- entity: weekly-timesheet
  shows:
  - Week
  - Submitted at
  - Total time
  - Billable time
- entity: account
  shows:
  - Name
entryPoints:
- web: /approvals
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/approvals.rs#Approvals
---

# Approvals

Submitted weeks across the team, filtered to those awaiting approval, those approved, or
all of them, with the total and billable time they hold.
