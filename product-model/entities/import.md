---
domain: importers
references:
- kind: code
  role: implementation
  target: crates/horae/src/models/jobs.rs
- kind: code
  role: implementation
  target: crates/horae/src/jobs.rs
- kind: spec
  role: intent
  target: specs/005-durable-harvest-jobs/spec.md
---

# Import

One run that brings Harvest data into Horae, from the Harvest connection or an uploaded Harvest
CSV export, either as a preview or for real.

## Information kept

- **Source** — the Harvest connection or an uploaded CSV file
- **Mode** — a preview that writes nothing, or a commit that applies the records
- **Scope** — a full pull, or only what changed since the last successful one
- **Counts** — created, updated, skipped and errored records for clients, projects, tasks and time entries
- **Record errors** — each record that could not be applied, and why

## States

### Queued

The import waits to start.

### Running

The import is reading and applying records.

### Completed

The import finished and its report is ready.

### Failed

The import stopped with an error.

### Cancelled

The import was cancelled on request.
