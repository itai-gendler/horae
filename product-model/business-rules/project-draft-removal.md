---
appliesTo:
- type: entity
  id: project-draft
  effect: removes
permits:
- related:
  - {verb: drafts, entity: manager}
- related:
  - {verb: drafts, entity: admin}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation.rs#discard_project_draft
---

# Only its own author discards a project draft

A draft is removed when its author discards it or creates the project from it.
