# PROPOSALS, ASSUMPTIONS AND NFR PROPOSALS

Every `[PROPOSAL]` and `[ASSUMPTION]` in any module must appear here with a
status. A missing row is an S8 failure.

## 1. Behavioral proposals

| ID | Module | Rule/AC | Statement | proposal_status | removal | Decision requested |
|---|---|---|---|---|---|---|
| P-001 | M001 | (R-M001-04) | <what is proposed> | pending | n/a | approve / reject |

`proposal_status: pending | approved | rejected`
`removal: pending | done (DEC-NNN)` — required once rejected, and stays
`pending` until the rule and its AC are physically gone from the module.

## 2. Assumptions

| ID | Module | Rule/AC | Assumption | Why the source is silent | assumption_status | removal |
|---|---|---|---|---|---|---|
| A-001 | M001 | (R-M001-05) | <assumption> | <source says nothing about X> | pending | n/a |

`assumption_status: pending | confirmed | rejected`
A `rejected` assumption is unblocked only when its rule is removed or
rewritten on a `[SRC]`/`[DERIVED]` basis and `removal: done (DEC-NNN)`.

## 3. NFR proposals

NFR proposals use `nfr_status` instead of `proposal_status`.
There is no `owner_accepted` value: an NFR is either in the spec
(`approved`) or out of it (`rejected` + rule removed).

| ID | Module | Rule/AC | NFR | nfr_status | removal |
|---|---|---|---|---|---|
| N-001 | M00N | (R-M00N-01) | <e.g. persistence of panel state> | pending | n/a |

## 4. Summary counters

- proposals pending: 0
- proposals rejected with removal pending: 0
- assumptions pending: 0
- assumptions rejected with removal pending: 0
- NFRs pending: 0
- NFRs rejected with removal pending: 0

These counters are informational; the verdict reads each row, not the
counters.
