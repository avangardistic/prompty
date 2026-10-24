# SPECIFICATION — README

This is the only file that carries a verdict label. It is written in P3.

## Verdict

verdict: <implementation-ready-full | implementation-ready-full-with-owner-review | requires-manual-review | requires-decisions-on-N-items>
N: <count of unique blocker IDs, or 0>
assigned_at: <date>
answerability_version: <n>
spine_version: <n>

No fifth label exists. `requires-manual-review` means S7 was not run under
any verification. `requires-decisions-on-N-items` means verification ran and
the spec is blocked.

## Report fields

| Field | Value |
|---|---|
| s7_result | not_run / pass / fail |
| report_status | verified_by_independent_reviewer / verified_by_owner / unverified |
| coverage_mode | full / spine_only / empty |
| answerability_version | 0 |
| checks_status | S1..S9 |
| in_scope_module_count | 0 |
| out_of_scope / abandoned / needs_revision | 0 / 0 / 0 |
| spine_rule_count / spine_rules_uncovered | 0 / 0 |
| assumption_resolution | 0 |
| assumption_rejected | 0 |
| assumption_rejected_resolved | 0 |
| nfr_pending | 0 |
| nfr_rejected_unremoved | 0 |
| scope_removed_modules | none |
| owner_accepted_partials | 0 |
| waived_questions | none |

Non-zero counts never change the label; they are printed next to it.

## Blockers

Required when the verdict is `requires-decisions-on-N-items`. One row per
unique blocker ID; symptoms are listed under their root cause and do not
increment N.

| Blocker ID | Root cause | Symptoms (not counted) | Single next action |
|---|---|---|---|
| B-PROP-P001 | proposal P-001 pending in (M003) | (M003) needs_revision | owner approves or rejects P-001 |

## Owner summary

**حکم:** `<label>` · **تعداد بلاکر یکتا:** `N`

| بلاکر | ریشه | علامت‌ها (شمرده نمی‌شوند) | اقدام بعدی |
|---|---|---|---|
| `B-...` | … | … | … |
