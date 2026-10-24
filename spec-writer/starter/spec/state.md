# STATE

phase: P0
phase_status: in_progress
owner_checkpoint: awaiting spine approval
last_updated: <YYYY-MM-DD>
execution_mode: agent_files | chat_blocks
output_root: spec/   # change only if the harness mandates another path (§16.1)

## Source
source_ref: <document name / date>
source_anchor_first: "<verbatim first sentence>"
source_anchor_last: "<verbatim last sentence>"
source_language: <fa | en | ...>
source_completeness: full | partial   # partial ⇒ S2/S9 not_run, blocker B-SOURCE

## Versions
spine_version: 0
answerability_version: 0

## Progress
in_scope_module_count: 0
out_of_scope_module_count: 0
abandoned_module_count: 0
needs_revision_module_count: 0
modules_total: 0
modules_written: 0
current_module: none
spine_rule_count: 0

## Checks
# S7 is derived: it always copies s7_result and is never set independently.
checks_status:
  S1: not_run
  S2: not_run
  S3: not_run
  S4: not_run
  S5: not_run
  S6: not_run
  S7: not_run
  S8: not_run
  S9: not_run

## S7
s7_result: not_run
report_status: unverified
coverage_mode: empty

## Open items
open_questions: 0
pending_proposals: 0
pending_assumptions: 0
pending_nfrs: 0

## Notes
- <one line per phase boundary, newest last>
