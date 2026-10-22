# Cetus Libraries Audits

Formal verification reports for Integer Mate and MoveSTL, the arithmetic and data-structure libraries used by Cetus protocols.

## Audit Reports

| Module | Auditor | Audit Duration or Date | Reviewed Commit | Report |
| --- | --- | --- | --- | --- |
| Integer Mate | Asymptotic | 2025-09-12 | `1fc772f61355de6b2be43275f909f120812c4bdc` | [Comprehensive Formal Verification](https://cetus.asymptotic.tech/integer-mate/fv-report.html) |
| MoveSTL | Asymptotic | 2025-09-12 | `0681fec63a310ae753d03a06f7c05d3e2925bb09` | [Comprehensive Formal Verification](https://cetus.asymptotic.tech/stl/fv-report.html) |

## Scope and Verification

### Integer Mate

**Scope:** Signed integer operations, unsigned wrapping and overflow-aware arithmetic, 256-bit word shifts, and full-width multiply-divide routines with defined rounding behavior.

**Methodology:** Sui Prover 1.5.3, using specifications against an unbounded mathematical integer model.

**Verification:** The report establishes numeric correctness and abort conditions for the covered operations. Consumer protocol logic and test modules are outside scope.

### MoveSTL

**Scope:** Skip lists, linked tables, primitive option wrappers and deterministic pseudorandom utilities used for skip-list level selection.

**Methodology:** Sui Prover 1.5.3, with specification preconditions and postconditions, ghost variables and Lean 4 models.

**Verification:** The report establishes accessor and containment properties. Some functions are modeled structurally or use axiomatized specifications, with their status tracked in the verification dashboard.

These reports apply to their specified revisions and verified properties.
