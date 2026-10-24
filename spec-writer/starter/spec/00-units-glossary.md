# UNITS AND GLOSSARY

Every term the source uses without defining, and every unit that appears in
a threshold, is defined here once. A rule that uses an undefined term is an
S7 unanswerable and usually an S1/S3 failure.

## 1. Units

| Term used in source | Canonical unit | Conversion | Source quote (if any) | Owned by |
|---|---|---|---|---|
| point | <price unit> | <1 point = ...> | "<verbatim>" | [PROPOSAL] if silent |
| pip | <price unit> | <1 pip = ...> | "<verbatim>" | |
| PipSize | <digits> | <formula> | "<verbatim>" | |

Rules:
- A numeric rule never uses a unit that is not defined in this table.
- If the source is silent on a conversion, the entry is `[PROPOSAL]` and
  appears in `proposals-assumptions.md`. It is never filled from external
  knowledge silently.

## 2. Glossary

| Term | Definition | Source quote | Status |
|---|---|---|---|
| <term> | <one-sentence definition> | "<verbatim>" | [SRC] / [DERIVED] / [PROPOSAL] / [ASSUMPTION] |

## 3. Ambiguous terms carried as questions

| Term | Why ambiguous | Question |
|---|---|---|
| <term> | <the two readings> | (Q-003) |
