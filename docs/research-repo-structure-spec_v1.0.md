# Research Repo — Structure Specification v1.0

*Drafted 2026-09-23. For the new `Historiotheque/Research` repository (GitHub org:
Historiotheque). Companion to the Studio Log Spec (v1.2).*

---

## 1. Purpose

The Research repo holds the **scholarly apparatus** of the practice: research questions,
literature reviews, bibliographies, and research methods. It is the counterpart to the
main Historiotheque repo, which remains the *release artifact* — the studio / sound lab /
research lab as cultural software, versioned with releases.

**Why separate:** daily research churn (question refinements, review drafts, bibliography
growth) does not belong in the release history of the main repo. A research repo also reads
as *scholarship* to academic stakeholders — the audience for the academic-credibility play.

## 2. Directory tree

```
Historiotheque/Research/
├── README.md                     # landing: what this repo is, how it's organized
├── docs/
│   └── research-repo-structure-spec_v1.0.md   # this file
├── research-questions/
│   ├── README.md                 # living index: clusters + statuses
│   ├── RQ-2026-001-<slug>.md
│   ├── …                          # one file per question
│   └── RQ-2026-NNN-<slug>.md
├── literature-reviews/
│   ├── README.md
│   └── <topic>-review.md          # e.g. cubism-documentability-review.md
├── bibliographies/
│   ├── README.md
│   └── <project>-BIBLIOGRAPHY.md  # per-project; cites the master by ID
├── BIBLIOGRAPHY.md               # master ANNOTATED bibliography (BIB-YYYY-NNN, Chicago)
└── methods/
    ├── README.md                 # method registry index
    └── M-2026-001-<slug>.md        # one file per method (populated as methods are adopted)
```

Folders are created by the uploads themselves — no scaffolding commit needed.

## 3. Research questions — file format

Each question is **one file**, named by its stable ID: `research-questions/RQ-2026-001-<slug>.md`.
The ID never changes; the file holds a dated activity log, so each question is both a
record and a log — the research counterpart to the studio log.

```markdown
# RQ-2026-001: <short title>

**Question:** ...
**Status:** open | refining | answering | answered | superseded
**Cluster:** <cluster name>
**Anchors:** <key texts, specs, releases — free text>

## Activity log
- 2026-09-20 — Question added.
- 2026-09-23 — Refined: ...
- 2026-10-04 — Superseded by RQ-2026-030.
```

**To add a question:** tell Oracle "add a research question" and state it. Oracle assigns the
next ID (`RQ-YYYY-NNN`), places it in a cluster (or starts a new one), writes the file,
updates the index, and reads it back for correction.

The `research-questions/README.md` is the living index: clusters with one-line questions and
status badges, regenerated from the files whenever the set changes.

## 4. Literature reviews — file format

One file per review: `literature-reviews/<topic>-review.md`, named by topic or by the RQ it
serves (`rq-2026-013-<slug>-review.md`). Free structure, but every review ends with two
fixed sections:

```markdown
## Works consulted
< BIB-YYYY-NNN citations, one per line >

## Open threads
< what the literature doesn't answer — candidate new RQs >
```

## 5. Bibliographies

- **Master** (`BIBLIOGRAPHY.md`, repo root): wide scope, **annotated** — each entry carries
  the author's note on why the source matters, not just the citation. Stable IDs
  (`BIB-YYYY-NNN`). Chicago author-date (per Studio Log Spec §8).
- **Per-project** (`bibliographies/<project>-BIBLIOGRAPHY.md`): cites the master by ID —
  no duplicated full citations. Project-specific annotations live here.
- **To add a citation:** tell Oracle "add a citation" and name the source. Oracle formats it
  in Chicago style, assigns the next ID, appends it to the master, and reads it back.

## 6. Methods — file format

Each adopted method is one file: `methods/M-2026-001-<slug>.md`, mirroring the RQ pattern:

```markdown
# M-2026-001: <method name>

**Description:** ...
**Status:** proposed | adopted | retired
**Used in:** RQ-2026-0xx, ... (questions this method serves)

## Activity log
- 2026-09-23 — Proposed.
- ... — Adopted / refined / retired.
```

The `methods/` folder ships as a **container with a format, not a taxonomy**: method names
are adopted from the author's research-design reading as it progresses, never invented by
the assistant. Candidate methods observed in the practice (proposed, not adopted) are listed
in `methods/README.md` for the author to confirm, refine, or reject.

## 7. Naming conventions

- Folders: kebab-case, plural nouns (`research-questions/`, `literature-reviews/`).
- Files: `<ID>-<slug>.md` for ID-bearing records; `<topic>-<word>.md` otherwise.
- IDs: `RQ-YYYY-NNN` (questions), `M-YYYY-NNN` (methods), `BIB-YYYY-NNN` (sources).
  Numbers are never reused; superseded records keep their files.

## 8. Cross-linking

- **Within the repo:** relative links (`../research-questions/RQ-2026-001-....md`).
- **To the main repo** (studio logs, releases, declarations): absolute GitHub URLs —
  cross-repo relative links don't resolve.
- **RQ ↔ studio log:** a log made while pursuing a question cites it (`related:` or body);
  a question's activity log notes the sessions that advanced it.
- **RQ ↔ refcard:** cards cite question IDs when the card bears on one; questions list
  card IDs under Anchors when relevant. Relevance is the whole rule (cf. Spec v1.2, R-110).

## 9. Migration plan

1. Create the repo on GitHub (Historiotheque org → New repository → `Research`, public).
2. **First task — the RQ split:** the existing `research-questions.md` (21 questions, clustered)
   is split into 21 per-question files plus the index README. Mechanical; done by Oracle as
   one upload batch with commit text.
3. Upload this spec to `docs/`.
4. Master bibliography seeded from existing reading lists; per-project bibliographies follow
   as projects need them.
5. Methods populate as the research-design reading progresses — the folder waits, ready.
