# MODULE MAP

module_count: 0
approved_by: none
approval_decision: none

`module_status` is filled in P2. Until then the cell holds `—`, which is
not a status value and is not legal after P2.

The count is derived from the requirements, never hardcoded. Requirements of
every category — behavioral, NFR, UI, persistence, constraint — become
modules the same way. No category is excluded a priori.

| ID | Module | Category | Requirements covered | Depends on | module_status |
|---|---|---|---|---|---|
| M001 | <name> | behavioral / NFR / UI / persistence / constraint | (REQ-01, REQ-02) | — | — |

The only legal values are `complete`, `complete_with_assumption`,
`needs_revision`, `out_of_scope`, `abandoned`.

## Module count derivation

| Category | Requirements | Modules |
|---|---|---|
| behavioral | <n> | <n> |
| NFR | <n> | <n> |
| UI | <n> | <n> |
| persistence | <n> | <n> |
| constraint | <n> | <n> |
| **total** | | **0** |

## Scope notes

- NFR modules only exist after their NFR proposal is `approved`.
- A module removed from scope needs `DEC-NNN: scope-removal MNN` naming the
  spine rules that touch it and the in-scope module that now implements each.
