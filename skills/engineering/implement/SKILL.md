---
name: implement
description: "Implement a piece of work based on a PRD or set of issues."
disable-model-invocation: true

session-shape:
  estimated-minutes: 75
  multi-session: false
---

Implement the work described by the user in the PRD or issues.

Use /tdd where possible, at pre-agreed seams.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

## Completion criteria — do NOT commit until these pass

Before committing, ALL of the following must exit 0:

1. **Metadata gate** — run `check_metadata.py` against the changed files.
   If the project has dist-brain metadata (@tags, @intent, etc.), the gate
   must pass. If the project has no dist-brain metadata, skip this step.

2. **Test suite** — run `pytest` (or the project's test command). Every test
   must pass. No skips, no xfail-as-pass — green means green.

3. **Typecheck** — run the project's typechecker (`mypy`, `pyright`, `tsc`,
   or equivalent). Zero errors.

If any of these fail, FIX the issue before committing. Do not commit
known-broken work. Do not rationalise skipping a step — if the step doesn't
apply to this project (e.g. no metadata, no typechecker), say so explicitly
and move on, but don't silently skip a step that does apply.

## After commit

Once the gate, tests, and typecheck are all green AND the work is committed:

4. Run `/review` to review the committed work.
