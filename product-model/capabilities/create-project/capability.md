---
domain: projects
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation.rs#finalize_project_draft
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation.rs#save_project_draft
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation/finalize.rs
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project.rs#NewProject
---

# Create project

A manager or admin sets up a new project for a client, with its billing, budget, tasks and team; the unfinished form is kept as a private draft.
