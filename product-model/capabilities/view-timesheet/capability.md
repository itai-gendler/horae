---
domain: timesheet
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/timesheet.rs#Timesheet
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/permissions/time_entries.rs#sheet
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries.rs#load_timesheet_page
---

# View timesheet

A person sees their own time for a day, a week or a calendar span, with daily and weekly totals.
