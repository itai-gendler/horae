---
domain: projects
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#get_project_overview
- kind: code
  role: implementation
  target: crates/horae/src/pages/projects.rs#ProjectList
- kind: code
  role: implementation
  target: crates/horae/migrations/0035_project_read_access.sql
---

# Browse projects

A person looks through the projects they may see, filtered by status, client and tag, with their budget progress.
