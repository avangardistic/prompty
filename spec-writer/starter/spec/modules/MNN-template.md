# MNN — <Module Name>
module_status: <complete | complete_with_assumption | needs_revision | out_of_scope | abandoned>
rewrite_count: 0

## 1. Purpose
<2–4 sentences: what this module decides and why it exists in the system.

## 2. Scope (In / Out)
- **In:** <what this module owns>
- **Out:** <what it must not do, and which module does it instead>

## 3. Inputs Owned

| Name | Type | Range | Default | Validation |
|---|---|---|---|---|
| <name> | <type> | <range> | <default> | <reject/accept rule> |

Validation failures are themselves rules (tagged) and carry pre/post.

## 4. Rules

For each rule:

- **ID:** R-MNN-01
- **Statement:** When <trigger>, the system shall <response>.
- **Tag:** [SRC: "<verbatim>"] / [DERIVED: "<quote a>" + "<quote b>"] / [PROPOSAL] / [ASSUMPTION]
- **status metadata:** only what applies — `proposal_status` / `assumption_status` / `nfr_status` / `removal`
- **pre:** <condition that must hold> OR "N/A — prohibition" / "N/A — pure function, inputs listed in section 3"
- **post:** <condition that holds afterwards> OR "N/A — prohibition" / "N/A — returns value only" / "N/A — no state change"

S3 fixed reasons by rule kind:

| Rule kind | pre | post |
|---|---|---|
| state-changing | required | required |
| prohibition | `N/A — prohibition` | `N/A — prohibition` |
| input constraint | required | `N/A — no state change` |
| pure computation / validation | `N/A — pure function, inputs listed in section 3` | `N/A — returns value only` |

A composite statement is split: if deleting one obligation still leaves a
complete rule with a different trigger, subject, or actor, it was two rules.

## 5. State

- **Owned:** <fields that exist only in this module>
- **Consumed:** <shared items, referencing 00-shared-state.md>
- **Interface:** per shared item — `read-only` / `write-only` / `read-write` / `write-only (creates)`

| Shared item | Interface | Note |
|---|---|---|
| SS-01 | read-only | |

## 6. Edge Cases

Numbered. "If <condition>, then <response>." Each edge case that changes
state must respect S3.

1. If <condition>, then <response>.

## 7. Acceptance Criteria

For each:

- **ID:** AC-MNN-01
- **Given:** <initial state> / **When:** <trigger> / **Then:** <observable result>
- **Test vector:** <in-range value; plus threshold and threshold ±1 where a threshold exists; or one worked example for a non-numeric AC>
- **Covers:** (R-MNN-01)

An AC that can carry neither a numeric vector nor a worked example is not an
AC: convert it to a rule plus an invariant (S4).

## 8. Invariants Preserved

| Spine rule | How this module preserves it |
|---|---|
| (SP-01) | <one line> |

## 9. Open Questions

```
Q-NN
question_status: open
Critical: yes | no
Context: <why it matters; what changes if unanswered>
Options:
  - option_1: <content> — Effect: <rule/AC/module that changes>
  - option_2: <content> — Effect: <...>
  - option_3: <content> — Effect: <...>
  - custom:   (Decision / Rationale / Affected / Edge cases) — Effect: <...>
```

## 10. Traceability

| Source sentence | Requirement ID | Rule ID(s) | AC ID(s) |
|---|---|---|---|
| "<verbatim>" | (REQ-01) | (R-MNN-01) | (AC-MNN-01) |
