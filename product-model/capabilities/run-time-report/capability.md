---
domain: reports
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/reports.rs#report_time
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/reports.rs#report_detailed
- kind: code
  role: implementation
  target: crates/horae/src/pages/reports.rs
---

# Run time report

A manager or admin reads the organization's time for a period, grouped and filtered.
