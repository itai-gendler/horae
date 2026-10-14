---
entities:
- entity: project
  shows:
  - Name
  - Code
  - Project type
  - Tags
  - Budget progress
- entity: client
  shows:
  - Name
entryPoints:
- web: /projects
- web: /projects/client/:client
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/projects.rs#ProjectList
---

# Projects

The projects a person may see, filtered by status, client and tag, with their budget progress.
