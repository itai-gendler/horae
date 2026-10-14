---
appliesTo:
- type: entity
  id: time-entry
  effect: reads
  contexts:
  - {place: 'web::team::reports'}
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/reports/limits/time.rs#authorize_current
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/reports.rs#report_time
---

# Only managers and admins report on the organization's time

Reports and their exports cover every person's time and are open only to managers and admins.
