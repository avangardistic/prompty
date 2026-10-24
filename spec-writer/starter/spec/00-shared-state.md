# SHARED STATE

Every item here is touched by more than one module. Each touching module
declares exactly one interface for it in its own `## 5. State` section, and
that declaration must match this file (S5).

## 1. Items

| ID | Item | Type | Range / domain | Initialised by | Read by | Written by |
|---|---|---|---|---|---|---|
| SS-01 | <name> | <type> | <range> | (M001) | (M002) | (M002) |

## 2. Interface matrix

`R` read-only, `W` write-only, `RW` read-write, `W+` write-only (creates).
A module that touches an item and is missing from this matrix is an S5
failure.

| Item | M001 | M002 | M003 |
|---|---|---|---|
| SS-01 | W+ | RW | R |

Rules:
- Exactly one module may hold `W+` per item; every other writer holds `W` or
  `RW`.
- An item written by two modules with no ownership note is an S5 failure.
- New shared state discovered during P2 is appended here immediately and
  recorded as `DEC-NNN: new shared state SS-NN` in `decisions.md`.
- A state item that lives only inside one module is not listed here; it is
  listed under that module's `Owned` fields.

## 3. Lifecycle

| Item | Created when | Destroyed when | Survives reset? |
|---|---|---|---|
| SS-01 | <event> | <event> | yes / no |
