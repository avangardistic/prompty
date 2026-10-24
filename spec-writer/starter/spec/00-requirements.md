# REQUIREMENTS

source_ref: <document name / date>
source_anchor_first: "<verbatim first sentence>"
source_anchor_last: "<verbatim last sentence>"

## 1. Requirements

| ID | Requirement (English) | Verbatim source quote | Category | Module(s) |
|---|---|---|---|---|
| REQ-01 | The system shall ... | "<source language, verbatim>" | behavioral / NFR / UI / persistence / constraint | (M001) |

Every source sentence stating a behavior, constraint, or invariant appears
in at least one row or is listed in section 2. A sentence that is neither
is an S2 failure.

## 2. Non-Normative Register

Sentences that state no requirement: examples, notes, emphasis, rationale.
They are exempt from S2 mapping only because they appear here verbatim.

| ID | Verbatim quote | Classification | One-word justification |
|---|---|---|---|
| NN-01 | "<source language, verbatim>" | example / note / emphasis | illustrative |

## 3. Source-level ambiguities found in P0

| ID | Ambiguity | Resolved by source? | Resolution / Q-NN |
|---|---|---|---|
| A1 | <term or rule that is undefined> | yes: "<quote>" / no | (Q-001) |

## 4. Coverage check

- source sentences stating behavior: <n>
- mapped to requirements: <n>
- registered as non-normative: <n>
- unresolved: <must be 0>
