---
appliesTo:
- type: entity
  id: project-draft
  effect: creates
permits:
- related:
  - {verb: drafts, entity: manager}
- related:
  - {verb: drafts, entity: admin}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation.rs#save_project_draft
---

# A project draft belongs to the manager or admin who started it

Each manager or admin keeps at most one private New project draft.
