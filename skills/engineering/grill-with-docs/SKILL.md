---
name: grill-with-docs
description: A relentless interview to sharpen a plan or design, which also creates docs (ADR's and glossary) as we go.
disable-model-invocation: true

session-shape:
  estimated-minutes: 15
  multi-session: false
---

Run a `/grilling` session, using the `/domain-modeling` skill.

## When to suggest `/decision-mapping`

`/grilling` sharpens intent; `/to-prd` synthesizes what is already known into a spec. If the grilling surfaces more than **3 open decisions that require research, prototyping, or discussion — and the answers cannot be resolved from the codebase alone** — the plan has real fog-of-war. Suggest `/decision-mapping` before `/to-prd`.

The user decides. Do not force a decision map when the fog is low, and do not let `/to-prd` absorb unresolved multi-session decisions by default.

Use `/decision-mapping` when:
- 4 or more decisions need external knowledge (research, API docs, third-party code)
- A decision needs a throwaway prototype to settle (use `/prototype`)
- A decision needs extended discussion with stakeholders (multi-session grilling)

Skip the map when:
- All open questions can be answered from the codebase
- The remaining decisions can be settled in the current session
- The path from idea to implementation is already clear
