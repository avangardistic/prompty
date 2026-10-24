# SPINE

spine_version: 0
approved_by: none
approval_decision: none

The spine holds cross-cutting invariants only. Every `SP-NN` must have at
least one implementing rule in an in-scope module (S6). Changing this file
requires a new `spine_version` and a `DEC-NNN`.

| ID | Invariant (one line) | Verbatim source quote | Tag | Implementing rule(s) |
|---|---|---|---|---|
| SP-01 | <invariant> | "<verbatim>" | [SRC] | (R-M001-01) |
| SP-02 | <invariant> | "<verbatim a>" + "<verbatim b>" | [DERIVED] | (R-M002-03) |
| SP-03 | <invariant> | — | [PROPOSAL] | (R-M003-02) |

Rules:
- Tag rules are identical to the module rules; a spine entry is a rule and
  is subject to S1, S3, S6, S8, S9 exactly like a module rule.
- A spine rule stays in force even when the module that suggested it is
  `out_of_scope` or `abandoned`; the scope-removal decision must name the
  in-scope module that now implements it.
- A spine rule with an empty `Implementing rule(s)` cell is an S6 failure
  and produces `B-SPINE-<id>`.

## Revision log

| spine_version | DEC | Change | Owner statement |
|---|---|---|---|
| 0 | — | initial draft | — |
