---
domain: importers
references:
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/credentials.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs
---

# Harvest connection

The organization's authorized, read-only link to one Harvest account, used to pull data from it.

## Information kept

- **Harvest account** — the Harvest account the connection reads from

## States

### Connected

Horae can read the Harvest account.

### Disconnected

The stored authorization is removed; the Harvest account it was bound to is remembered for a reconnect.
