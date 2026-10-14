---
domain: projects
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/reports.rs#export_projects_csv
- kind: code
  role: implementation
  target: crates/horae/src/reports.rs#export_projects_xlsx
- kind: code
  role: implementation
  target: crates/horae/src/reports/limits/project.rs
---

# Export projects

A person downloads the projects they may see as CSV or Excel.
