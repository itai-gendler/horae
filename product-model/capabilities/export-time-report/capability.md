---
domain: reports
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/reports.rs#export_csv
- kind: code
  role: implementation
  target: crates/horae/src/reports.rs#export_xlsx
- kind: code
  role: implementation
  target: crates/horae/src/reports/limits/time.rs#authorize_current
---

# Export time report

A manager or admin downloads the time behind the current report as CSV or XLSX.
