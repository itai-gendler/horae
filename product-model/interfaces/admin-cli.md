---
type: cli
actors:
- operator
- admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/cli.rs#Commands
- kind: code
  role: implementation
  target: crates/horae/src/main.rs
- kind: code
  role: implementation
  target: crates/horae/src/cli/imports.rs
- kind: doc
  role: intent
  target: README.md
---

# Command line

The `horae` server binary's administrative commands: the bootstrap and user commands the
operator runs on the server, and the import commands an admin runs against a running server
with a saved session.
