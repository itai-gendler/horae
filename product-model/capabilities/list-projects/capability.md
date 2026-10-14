---
availability:
- {place: harvest-api}
references:
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#list_projects
- kind: code
  role: implementation
  target: crates/horae/src/harvest/project_reads.rs
---

# List projects

An integration acting with a person's session reads the projects whose progress that person may follow through the Harvest-style API.
