# Error Taxonomy for Art Operations — v0.1 (draft)

*Historiotheque / Research. Drafted 2026-09-25 from the operator's field notes
(walk recordings + notebook). Status: draft — open for revision, correction,
and reclassification. Unclassifiable errors go in class 10; the taxonomy is
never closed.*

## Why this exists

An Art Operation that keeps an audit trail but has no account of its failure
modes is keeping half a record. The operator makes mistakes — distraction,
fatigue, hunger, absent-mindedness, false beliefs — and so do the systems
around him. This taxonomy names the error classes, grades their severity, and
states what happens when they compound. It is the risk-management layer of the
operation: checklists, failsafes, and heuristics are built on top of it, not
beside it.

## The severity scale

| Level | Name | Definition |
|---|---|---|
| S1 | Negligible | Cosmetic. Caught immediately or on next review. No rework beyond the fix itself. |
| S2 | Minor | Rework required, contained. Costs time or materials; the record stays intact. |
| S3 | Major | Loss of work product, recoverable with effort. The record has a gap that must be marked. |
| S4 | Severe | Loss of irreplaceable record, or damage to the operation's credibility. Recovery is partial at best. |
| S5 | Catastrophic | Harm to people, or loss of the Cultural Treasure across generations. Irreversible. |

Severity is assessed per incident, not per class: any class can in principle
reach any level, but each class has a *typical* range, noted below.

## Blast radius

Borrowed from engineering: the area affected when an error detonates. A
misfiled index card has a blast radius of one drawer. A transcription error in
a transmitted text has a blast radius measured in generations. Severity says
how bad; blast radius says how wide. Both go in the incident record.

## The classes

### 1. Accounting errors
Errors of calculation, measurement, counting, inventory. Typical range: S1–S5.
The canonical case: the art operation of building a cathedral. A single
measurement error can propagate through the structure — catastrophic
consequences (S5): the building fails, people are maimed or killed, a
century-long intergenerational project is lost. In the Historiotheque the
milder form is inventory error: counts that don't reconcile, works whose
location is unknown. Mitigation: independent recount, reconciliation against
the record, never a single pair of eyes on load-bearing numbers.

### 2. Transcription errors
Errors introduced when a work or record is copied, converted, or transmitted —
the hand slips, the format migrates, the link rots, the file corrupts.
Typical range: S2–S5. This is the failure mode of the Cultural Treasure in
transit: every faithful transmission across generations passes through a
chain of transcriptions, and each link can corrupt. Blast radius grows with
every downstream copy made from the corrupted source. Mitigations, all in
current practice: redundant copies (distributed logs), format migration with
verification, and audit passes — e.g. the planned audit of the Declarations'
Markdown against the original HTML exports, which exists precisely because
conversion drops content.

### 3. Interpretation errors
Errors of reading: the original meaning and intention of a work is not
available, and the gap is filled wrongly — or filled with false confidence.
Typical range: S2–S4. A special case: the record is absent. You cannot
reconstruct what you don't have access to; if it isn't in the record, or was
lost to transcription error (class 2 — link rot, data corruption by another
name), interpretation proceeds on nothing. The honest form of this error is
declared ignorance ("the record does not say"); the dangerous form is
confident reconstruction presented as fact. Mitigation: mark every
reconstruction as reconstructed (standing rule); prefer the gap over the
guess. The hermeneutics of Art Operations — the theory of all this — is
future work.

### 4. Methodology / technique errors
The wrong method for the task, or the right method executed without its
conditions. Typical range: S1–S4. Distinct from operator error (class 8): here
the *choice* is wrong, not the execution. Includes errors of technique at the
workbench. Mitigation: method selection recorded in the log (so the choice is
auditable), and the Pattern Language's growing catalog of what works.

### 5. Workflow management errors
Errors of sequencing, scheduling, and dependency: the right tasks in the wrong
order, the prerequisite skipped, the handoff dropped. Typical range: S1–S3.
The Switchboard Method exists largely to bound this class — single-machine
scheduling with explicit next moves leaves less room for the sequence to rot.

### 6. Workspace management errors
Errors of the physical or digital environment: the tool not where the hand
expects it, the file not where the procedure says it is, the workspace
arranged against the work instead of for it. Typical range: S1–S3. Small,
Taylorist costs — each one trivial, all of them compounding into the day's
friction. Mitigation: workspace setup as procedure, reviewed like any other.

### 7. System errors
Flaws in the system design itself: the way of working wastes energy, time, or
attention structurally — not a mistake *in* the system but a mistake *of* the
system. Typical range: S2–S4. The signature is recurrence: the same failure
keeps happening no matter how careful the operator is, because the procedure
demands more than the operator has. Mitigation: redesign the procedure, not
the person. (This is where the scale-down doctrine lives: a system that
requires heroics to function is a system error.)

### 8. Operator errors
The operator is distracted, tired, hungry, absent-minded, or reasoning from a
false belief — an inaccurate representation of the current state of affairs.
Typical range: S1–S3, but the *frequency* is the highest of any class, which
is what makes it load-bearing. This is the class the whole failsafe apparatus
answers to: checklists, heuristics written into the record, procedures that
assume the operator is fallible and proceed anyway. Aviation learned this a
century ago; the operation learns it now. No procedure that requires a perfect
operator is a procedure.

### 9. Communication / signaling errors
The message sent is not the message received — or the sending itself costs
more than the message is worth. Typical range: S1–S3. Includes the cost of
sending (the "Cost of Ping": every message spends attention, the scarcest
resource in the operation) and the risks of the channel (ambiguity, delay,
misreading). Note the inversion that governs the operation's public record:
costly signaling is also *honest* signaling. A public audit trail maintained
daily for years is expensive to fake and cheap to check — which is exactly why
it is credible. The handicap principle, applied to the archive.

### 10. DON'T KNOWS
The junk drawer, per the faceted-taxonomy discipline: errors that cannot yet
be classified, categorized, or tagged. Typical range: ungraded. This class is
never empty and never closed — it is where new classes are born. Review it
regularly; anything that sits here twice earns its own classification pass.

## Compounding

Errors rarely arrive alone, and severity does not add — it multiplies. Two
simultaneous S2s routinely produce an S4: a transcription error (class 2)
plus an interpretation error (class 3) yields a corrupted record read with
false confidence — worse than either alone. The incident record therefore
notes *co-occurring* classes, not just the headline error. Rule of thumb: when
two classes coincide, assess severity one level above the worse of the two,
then check whether that was pessimistic enough.

## Mitigations, mapped

| Class | Primary mitigation | Instrument |
|---|---|---|
| 1. Accounting | Independent recount; reconciliation | Checklists; inventory procedures |
| 2. Transcription | Redundancy; verified migration; audits | Distributed logs; Zenodo; conversion audits |
| 3. Interpretation | Mark reconstructions; prefer the gap | Reconstruction-marking rule; no-backfill doctrine |
| 4. Methodology | Record the choice; consult the catalog | Studio logs; Pattern Language |
| 5. Workflow | Explicit sequencing | Switchboard Method; next-move cards |
| 6. Workspace | Setup as procedure | Workspace procedures |
| 7. System | Redesign the procedure | Scale-down doctrine; method review |
| 8. Operator | Assume fallibility | Checklists; failsafes; heuristics in the record |
| 9. Communication | Price the message; check receipt | Cost-of-Ping discipline |

## Relation to neighboring instruments

- **Checklists** are the executable form of this taxonomy: each checklist item
  is a named error that will not happen today.
- **The Pattern Language** holds the positive form (what works); this
  taxonomy holds the negative form (what fails). They are companion documents.
- **Logistics** (inventory, storage, insurance) and **Risk** are the
  operational folders where this taxonomy is applied. Proposed placement:
  `Research/risks/` for this document; `Research/logistics/` for the
  logistics material.
- **Research questions** touching error, risk, and failure should cite this
  taxonomy by version once adopted.

## Changelog

- v0.1 (2026-09-25): drafted from the operator's field notes. Ten classes,
  five severity levels, compounding rule, mitigation map. Open for revision.
