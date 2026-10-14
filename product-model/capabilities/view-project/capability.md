---
domain: projects
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#get_project_details
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects/detail_view.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#get_project_fee_balances
---

# View project

A person opens one project with its details, tasks, team, budget progress and fee balances.
