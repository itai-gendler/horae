---
appliesTo:
- type: entity
  id: project
  effect: creates
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation.rs#finalize_project_draft
---

# Only managers and admins create projects

Projects are created by managers and admins, from New project or through imports.
