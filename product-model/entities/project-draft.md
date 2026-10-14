---
domain: projects
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/project_creation.rs#save_project_draft
- kind: code
  role: implementation
  target: crates/horae/src/pages/new_project/draft.rs
---

# Project draft

The unfinished New project form of one manager or admin, kept privately so they can leave and
resume it.

## Information kept

- **Settings** — everything entered so far for the new project
- **Saved at** — when the draft was last saved
