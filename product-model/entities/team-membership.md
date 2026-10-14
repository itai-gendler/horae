---
domain: projects
references:
- kind: code
  role: implementation
  target: crates/horae/src/models/project_creation.rs#ProjectMemberInput
- kind: code
  role: implementation
  target: crates/horae/migrations/0001_init.sql
---

# Team membership

A person's place on one project's team, which lets them track time on it.

## Information kept

- **Project role** — Project manager or Project member
- **Billable rate** — the person's billable rate on this project, when it overrides their usual rate
- **Cost rate** — the person's cost rate on this project, when it overrides their usual cost
- **Budget** — the person's share of the budget, when the project budgets per person
