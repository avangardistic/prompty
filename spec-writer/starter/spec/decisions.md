# DECISIONS

One `DEC-NNN` per decision. IDs are sequential and never reused.
Owner answers are quoted verbatim in the owner's own language inside the
`Owner words` column; that quotation is the only permitted non-English
prose in a spec file.

| ID | Date | Phase | Type | Subject | Decision | Owner words | Effect on rules/AC/spine |
|---|---|---|---|---|---|---|---|
| DEC-001 | <date> | P0 | spine-approval | SP-set v1 | approved / modified / rejected | "<verbatim>" | <what changed> |
| DEC-002 | <date> | P1 | question-answer | Q-001 | option_2 / custom | "<verbatim>" | (R-M001-03) |
| DEC-003 | <date> | P2 | new-shared-state | SS-05 | added | "<verbatim>" | (M003) |
| DEC-004 | <date> | P2 | scope-removal | M004 | out_of_scope | "<verbatim>" | spine rules touched: (SP-04) now implemented by (M002) |
| DEC-005 | <date> | P3 | waive-question | Q-007 | waived | "<verbatim>" | affects no rule, AC, or spine rule |
| DEC-006 | <date> | P3 | rejected-assumption-removal | A-003 | rule removed | "<verbatim>" | (R-M002-05) deleted; (AC-M002-04) deleted |

## Type vocabulary
`spine-approval`, `module-map-approval`, `question-answer`,
`new-shared-state`, `scope-removal`, `waive-question`,
`rejected-proposal-removal`, `rejected-assumption-removal`,
`rejected-nfr-removal`, `partial-resolution`, `escalation`.

## Rules
- A decision that changes `00-spine.md` also increments `spine_version`.
- A decision that changes a rule, an AC, or a module status after an S7 run
  increments `answerability_version` and forces a fresh S7.
- Deleting a decision is forbidden; supersede it with a new `DEC-NNN`.
