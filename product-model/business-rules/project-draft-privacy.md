---
appliesTo:
- type: entity
  id: project-draft
  effect: reads
permits:
- related:
  - {verb: drafts, entity: manager}
- related:
  - {verb: drafts, entity: admin}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation.rs#load_project_draft
---

# Only its own author sees a project draft

A project draft is never shown to anyone but the person who started it.
