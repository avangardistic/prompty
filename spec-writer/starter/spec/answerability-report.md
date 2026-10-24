# ANSWERABILITY REPORT

This file records check results and S7 only. It contains NO verdict label. The
verdict is written exclusively in `README.md` under `## Verdict`.

answerability_version: 0
report_status: unverified
coverage_mode: empty

## 1. Static checks

| Check | Result | Evidence (file / rule IDs) | Note |
|---|---|---|---|
| S1 Tag Completeness | not_run | | |
| S2 Source Traceability | not_run | | |
| S3 Contract Completeness | not_run | | |
| S4 Test Vector | not_run | | |
| S5 Shared State Consistency | not_run | | |
| S6 Spine Integrity | not_run | | |
| S7 Answerability Test | not_run | | derived: copies `s7_result`, never authored |
| S8 Proposal/Assumption Honesty | not_run | | |
| S9 Derived Traceability | not_run | | |

Allowed values: `pass` / `fail` / `not_run`.
`not_run` is required when the source text was unavailable for S2 or S9; in
that case the root blocker is `B-SOURCE`, not `B-CHK-S2`/`B-CHK-S9`.

## 2. S7 run

s7_result: not_run
in_scope_module_count: 0
spine_rule_count: 0
question_count_required: 0
question_count_asked: 0

Counts:
- C (critical total): 0
- FC (critical answered fully): 0
- P (noncritical total): 0
- FP (noncritical answered fully): 0
- RP (noncritical resolved by owner): 0
- OP (noncritical still open): 0

Coverage:
- modules_with_zero_questions: <list | none>
- spine_rules_with_zero_questions: <list | none>
- group with zero questions: `<group>: 0 questions — vacuously satisfied`

Pass criteria applied literally:
- `FC == C` → <true/false>
- `OP == 0` → <true/false>
- `FP * 10 >= 9 * P` (no rounding) → <true/false>
- all in-scope modules and all spine rules covered → <true/false>

## 3. Question records

| ID | Target (module / spine) | Question | Critical? | Score | Answered by |
|---|---|---|---|---|---|
| Q-S7-01 | M001 | <text> | yes/no | fully/partial/unanswerable | independent reviewer / owner |

Scores are frozen for this `answerability_version`. Owner decisions after
scoring set `partial_resolution` in `open-questions.md` (and a `DEC-NNN` in
`decisions.md`); they never change these scores.

## 4. Execution record

- Pre-flight: <independent reviewer available | owner manual review | owner declined>
- Reviewer saw only: <spec + source | spec only>
- report_status: <verified_by_independent_reviewer | verified_by_owner | unverified>
- Run at: <date>
- Invalidated by: <change | none>
