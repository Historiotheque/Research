# risks/

Risk management for the Art Operation: the error taxonomy, its severity
scale, and its applications.

## Contents

- `error-taxonomy-v0.1.md` — the ten error classes (accounting, transcription,
  interpretation, methodology/technique, workflow, workspace, system, operator,
  communication/signaling, DON'T KNOWS), the S1–S5 severity scale, blast
  radius, compounding rules, and the mitigation map.

## How this folder is used

- The taxonomy is the risk-management layer of the operation: checklists,
  failsafes, and heuristics are built on top of it, not beside it.
- Each checklist item is a named error that will not happen today — the
  checklist is the executable form of this taxonomy.
- Incident records cite the taxonomy version they were assessed against.
- Companion document: *A Pattern Language for Art Operations* — the Language
  holds the positive form (what works); this folder holds the negative form
  (what fails). The two cite each other.
- The taxonomy is never closed: unclassifiable errors go in class 10
  (DON'T KNOWS) until they earn their own classification.
