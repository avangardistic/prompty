# OPEN QUESTIONS

Every `Q-NN` lives here. Question text is English (spec file); the owner's
answer is quoted verbatim in `decisions.md`.

```
Q-001
question_status: open
Target: (M001) / (SP-03) / cross-module
Critical: yes | no
Context: <why it matters and what changes if unanswered>
Options:
  - option_1: <content> — Effect: <rule/AC/module that changes>
  - option_2: <content> — Effect: <...>
  - option_3: <content> — Effect: <...>
  - custom:   (Decision / Rationale / Affected / Edge cases) — Effect: <...>
Resolution: <DEC-NNN | none>
partial_resolution: open | owner_accepted | converted_to_assumption
```

## Status values
`question_status: open | open_owner_allowed | answered | waived`

- `answered` — a `DEC-NNN` records the chosen option.
- `waived` — `DEC-NNN: waive Q-NN` states that no rule, AC, or spine rule is
  affected. A waived question never blocks.
- `open_owner_allowed` — the owner allowed it to stay open knowing that it
  still blocks the ready verdict. Requires `DEC-NNN: keep Q-NN open`, it
  stays counted as `B-QUESTION-<id>`, and it is never a pass.

## Bank

| ID | Target | Status | Critical | Resolution | partial_resolution |
|---|---|---|---|---|---|
| Q-001 | (M001) | open | yes | none | open |
