# CHANGELOG

## v5 — harness-aware, principles made mechanical

1. **Execution modes replace the capability table.** §2 now names two
   delivery modes — file tools present, file tools absent — and records the
   choice as `execution_mode` in `state.md`. The previous version left the
   mode implicit, so a harness run and a chat run could diverge without
   anyone noticing. Both modes must now produce identical file content.
2. **New §16 — operating inside a harness.** Precedence against harness or
   project instructions, resume-from-`state.md`, recovery after compaction,
   tool discipline (no builds, tests, linters or shell commands), chat-volume
   rule, long-source handling, non-interactive checkpoints, and the rule that
   a sub-agent may do exactly one job: the independent review.
3. **§6 rewritten around the four Karpathy principles of the current
   guidelines** — think before writing, simplicity first, surgical changes,
   goal-driven execution — each with its own test, plus an enforcement table
   mapping every principle to the rule and the check that actually enforces
   it. No principle is left as advice, and the document now states the
   observable signal that the principles are working.
4. **Simplicity made falsifiable.** "Any extra file is a rejection, not a
   preference" replaces the softer phrasing, so §5's closed list is testable.
5. **§14 gained a cross-turn surgical rule.** A delivered file is never
   cleaned up on a later turn unless a check failure or a decision requires
   it, which extends §6.3 beyond a single turn.
6. **§15 gained three prohibitions** that were implicit before: never restart
   from P0 over recorded progress, never run a build/test/linter to verify a
   spec, never add a file/section/field/check outside the list.
7. **Persian annex moved to §17 and de-duplicated.** Its repeated never-do
   list was removed (it now points at §15), and a mode table was added so the
   owner can see the three practical cases without reading English.
8. **FIELD vocabulary extended** with `execution_mode` and `output_root`, both
   bookkeeping rather than state.

## v4 — portable, model-agnostic, bilingual

1. **No vendor or model name anywhere.** The role line no longer says which
   product runs the prompt, and S7's pre-flight no longer says which kind of
   sub-agent to spawn. Any required capability is now defined by what it must
   do (section 2), with an explicit fallback when it does not exist.
2. **Chat-only mode defined.** When the environment cannot write files, every
   file is emitted as a fenced block with its path and full current content.
   Previously the prompt assumed a file-writing agent; in a plain chat it
   would have silently produced nothing usable.
3. **Persian annex added (section 16).** Persian explanation of the four
   operating principles, the language split, the four verdict labels, and the
   literal Persian strings for checkpoints, the question template and the
   final report. The English core stays normative and the annex says so.
4. **S7 count names disambiguated.** S7 reused `N` for noncritical questions
   while the verdict used `N` for unique blockers, making
   `requires-decisions-on-N-items` unreadable. Counts are now
   `C / FC / P / FP / RP / OP`.
5. **S7 pass criteria made satisfiable.** `FN * 100 >= 98 * N` demanded a
   100% fully-answered rate for every `N < 50`, which made the owner's
   `partial_resolution` path unreachable: condition 7 could be satisfied and
   S7 still failed. Replaced with `FC == C`, `OP == 0`, and
   `FP * 10 >= 9 * P`; condition 7 now reads the same field as S7 criterion 2,
   so gate and check cannot disagree.
6. **`checks_status.S7` declared derived.** It previously existed both as a
   check row and as `s7_result`, with no rule for which wins. It now always
   copies `s7_result` and is never authored independently.
7. **Orphan requirements closed.** S2 was one-directional (source → REQ); a
   requirement could be extracted and never implemented. Direction (b) now
   requires every `REQ-NN` to reach a rule in an in-scope module or a logged
   scope decision, with blocker `B-REQ-<id>`.
8. **`B-SOURCE` added.** A missing or partially read source previously
   surfaced as `B-CHK-S2`, which pointed at a check instead of the actual
   action. `B-SOURCE` is the root and suppresses the S2/S9 rows.
9. **Blocker attribution rule generalized.** The v3 per-case suppression list
   became one rule: every failed observation is attributed to exactly one
   blocker or is itself a blocker; symptoms are written with `→`. `N` is now
   computable without case analysis. This includes the case where S7 fails
   only because of open partials or an uncovered spine rule: `B-S7` becomes a
   symptom of `B-PARTIAL` / `B-SPINE` instead of a second count.
10. **P0 stall contradiction fixed.** The third rejected spine draft wrote
    `B-SPINE`, a per-rule ID that cannot represent a stall, and left no
    unblocking path. It now opens a `Q-NN` and counts as `B-QUESTION-<id>`.
11. **Domain hardcode removed.** The role prohibited "MQL5 code" while the
    goal promised no domain assumption; it now prohibits code in any language.
12. **Karpathy-aligned operating principles (section 6).** The four current
    principles — think before writing, simplicity first, surgical changes,
    goal-driven execution — are stated as binding, with a per-phase
    write → check → fix loop and a mechanical exit for each phase.

## v3 — fixes applied in the previous pack

1. **Version counters reclassified.** `spine_version` and
   `answerability_version` were listed under STATUS although they are not the
   state of any module, phase, check, report, proposal, assumption, question,
   or partial. They are now FIELD entries with a one-line justification, so
   the STATUS vocabulary matches its own definition.
2. **Blocker double-count removed.** `B-CHK-<S1..S9>` overlapped with
   `B-S7`, `B-EMPTY`, and `B-SPINE`, which made `N` ambiguous. The row now
   covers S1–S6, S8, S9, and a new *check-vs-cause rule* states exactly when
   `B-CHK-<id>` is suppressed: S6 failures caused by an uncovered spine rule
   count as `B-SPINE` only; S7 failures are always `B-S7`; `B-EMPTY`
   suppresses the check IDs it implies; S1, S3, S4, S5, S8, S9 always count.
3. **Templates added.** Thirteen starter files under `starter/spec/` now
   match the prompt's own vocabulary, including `coverage_mode`, `removal`,
   `waive`, `answerability_version`, and the ten-section module template.
4. **No "previous version" reference.** The module template is reproduced in
   full inside the prompt, so the file is self-contained.

## v2 — fixes carried forward

- Checks S1–S9 now feed the verdict (condition 1); before, only `s7_result`
  was an input and a spec could violate S1/S3/S5 and still be labelled ready.
- `requires-manual-review` and `verified_by_owner` reconciled: owner review is
  allowed but its label states that no independent review happened.
- S7 outputs enumerated (result, report_status, coverage_mode, records,
  counts) so "S7 produces only two outputs" no longer contradicts the
  coverage and scoring requirements.
- `answerability_version` added: scores are frozen per version, so a critical
  partial is no longer a permanent dead end.
- `open_owner_allowed` no longer both allowed in P1 and blocking in condition
  8: `waived` with a `DEC-NNN` was added, and waiver requires proof that no
  rule, AC, or spine rule is affected.
- `B-SCOPE` added: an `out_of_scope` module without a decision previously
  failed condition 6 while having no blocker ID, so `N` was uncountable.
- Dedup restated as one rule: root causes are counted, symptoms are not, and
  `B-MOD` never counts alongside an upstream blocker for the same module.
- Non-vacuity added (condition 9 + `B-EMPTY`): an empty spec could previously
  pass every vacuous condition and be labelled ready.
- Domain hardcoding removed: the EA spine checklist and the A1–A10 seeds now
  apply only when the source is an EA/trading system.
- Seed items that were really instructions (UI capture, NFR silence) moved
  out of the ambiguity list into *Pre-seeded decisions*.
- `source_ref` + `source_anchor` replace the forbidden hash: verbatim
  verifiability without tooling.
- S2/S9 declared to require the source text, so the claim that every check is
  executable is true.
- Operational definitions added for S1 (deletion test), S2 (Non-Normative
  Register), S6 (exit condition and uncovered spine rule), S3 (per-kind
  pre/post table), S4 (threshold ±1, worked example).
- `rewrite_count` capped at 3 with an escalation path instead of an infinite
  loop.
