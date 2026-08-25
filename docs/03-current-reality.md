# Current reality and migration notes

Read [00 — Mental model](00-mental-model.md) first if you are new.

This page is the **Reality Map**. Law is frozen. Implementations and optional proposals move. Fragmentation is listed here; it is not hidden.

---

## Intended architecture

```text
META (method)  ──produces / governs──►  CORE (law)
CORE  ──must remain explainable by──►  META tests
Implementations ──claim alignment without amending──►  this charter
```

- One official name: **CEK**.
- One closed L1 set: **Host** (decide) and **Peer** (apply).
- Shared-world change is Intent under Cap → Result of Ops → apply → lineage → reverse.
- Baseline is permanent. Profile never grants Cap.
- This repository states law. It does not ship kernels.

---

## Actual state

Cartography of the live tree at SHA `2a0d17a` (docs pass built on top). Existing README / CORE / META were treated as **evidence**, not as authority over the tree. The tree won.

### This repository

| Fact | Evidence |
|------|----------|
| Documentation-only charter | `find` of the tree: Markdown + Mermaid; no source, tests, package manifest, or CI |
| META 00–10 frozen | [`CHARTER.md`](../CHARTER.md), [`META/`](../META/) |
| CORE 00–27 frozen, including hardening 14–27 | [`CHARTER.md`](../CHARTER.md), [`CORE/`](../CORE/) |
| PROPOSALS unfrozen | [`PROPOSALS/README.md`](../PROPOSALS/README.md) |
| Conceptual freeze complete for law | [`COMPLETENESS.md`](../COMPLETENESS.md) |
| Last charter commit before this reader-path pass | `2a0d17a` (2026-08-15) — INDEX pointer to implementations + S-tier scorecard |

### What moved outside this repo after 2026-08-15

INDEX already named [cek-runtime](https://github.com/bitplorer/cek-runtime) and [cek-python](https://github.com/bitplorer/cek-python). The live sibling set is larger:

| Repo | Role | In INDEX before this pass? |
|------|------|----------------------------|
| [cek-runtime](https://github.com/bitplorer/cek-runtime) | Rust Host/Peer kernels, contract, vectors, CLI | Yes |
| [cek-python](https://github.com/bitplorer/cek-python) | `cek-host` + `cek-surface` | Yes (INDEX only; README glance omitted it) |
| [cek-hw](https://github.com/bitplorer/cek-hw) | L5 `hw.*` driver, serial, MCU port. Not a Host. | **No — created 2026-08-25** |
| [ux-app](https://github.com/bitplorer/ux-app) | L7 application on ux-dom + ux-channel | No (out of charter scope; listed here as L7 existence) |

This is not a law gap. It is a **map** gap, closed by this page and the hub updates.

### Dual path: CORE 25–27 vs PROPOSALS P1/P4

Not competing law.

| Topic | CORE (rule) | PROPOSALS (rationale) |
|-------|-------------|------------------------|
| Idempotency bind | [`CORE/26`](../CORE/26-idempotency.md) — optional, not required for Baseline; fail closed if bind required and store down | P1 — still listed as unfrozen recommendation |
| Apply receipt | [`CORE/25`](../CORE/25-landed-and-receipts.md) — optional for Baseline; reverse prefers landed set when present | P4 — still listed as unfrozen recommendation |
| Recovery Cap | [`CORE/27`](../CORE/27-recovery-cap.md) — explicit Cap for compensation | Compensation already in CORE/09; P3 is the stricter profile |

**Rule in force:** CORE 25–27 are charter-frozen conceptual rules (optional for Baseline). PROPOSALS keeps the adoption rationale and the remaining unfrozen items (P2, P3, P5–P8). Production profiles enable receipts and idempotency; Baseline stays valid without them.

### Soft language inside frozen CORE

[`CORE/03-axioms.md`](../CORE/03-axioms.md) notes projection determinism with “should”. That sentence is existing frozen text. The reader-facing law on this spine states the Host pipeline as ordered stages ([`CORE/06`](../CORE/06-host-peer.md)) and does not relax it.

---

## Public surface (stable)

| Surface | Where |
|---------|--------|
| Official name CEK | [`CORE/00-overview.md`](../CORE/00-overview.md) |
| Axioms A1–A10 | [`CORE/03-axioms.md`](../CORE/03-axioms.md) |
| Frozen vocabulary | [`CORE/04-vocabulary.md`](../CORE/04-vocabulary.md) |
| Canonical story | [`CORE/13-canonical-story.md`](../CORE/13-canonical-story.md) |
| Kill criteria K1–K14 | [`KILL-CRITERIA.md`](../KILL-CRITERIA.md) |
| Conformance families | [`CORE/19-conformance.md`](../CORE/19-conformance.md) |
| Stability guarantees | [`STABILITY.md`](../STABILITY.md) |
| Charter freeze / amendment | [`CHARTER.md`](../CHARTER.md) |

---

## Experimental / incomplete (not gaps in law)

| Item | Status |
|------|--------|
| PROPOSALS P2 Op effect class | Unfrozen. Baseline default if adopted: treat unknown class as mutate |
| PROPOSALS P3 Strict reverse profile | Unfrozen optional profile |
| PROPOSALS P5 Baseline manifest | Unfrozen; conceptual manifest already sketched in CORE/11 |
| PROPOSALS P6 Time-boxed Activities | Unfrozen L6/L7 policy |
| PROPOSALS P7 Hash-chained lineage | Unfrozen optional L6 |
| PROPOSALS P8 Grantor/Cap separation emphasis | Already implied by CORE/14 and CORE/15 |
| Executable conformance vectors | Specified as **families** here; published vectors live in implementations |
| Domain Op catalogs | L5 — never this repo |
| Cap cryptography, wire field paths, SLOs | Out of scope by design |

---

## Documentation stance

**Clean happy path first** ([00](00-mental-model.md), [01](01-architecture-and-ownership.md), [02](02-happy-path.md)) **+ honest current reality** (this page).

- CORE and META remain the authority. This `docs/` spine is the map, not a second vocabulary.
- Existing files are kept. Nothing in CORE/META/PROPOSALS was deleted for this pass.
- Hub docs (README, INDEX, CONCEPTS, COMPLETENESS) point here; power stays in CORE.

---

## Cartography proof

Commands run against the live clone before any reader-facing prose:

- `git clone https://github.com/bitplorer/cek-framework.git`
- `git log --oneline`, `git ls-tree -r HEAD`, `find . -not -path './.git/*'`
- Full read of README, INDEX, CHARTER, CHOICES, COMPLETENESS, CONCEPTS, CONTRIBUTING, GLOSSARY, KILL-CRITERIA, STABILITY, STYLE
- Full read of CORE 00–27, QUICKSTART, SUMMARY; META 00–10, SUMMARY; PROPOSALS; all `diagrams/*.mmd`
- Sibling README read: cek-runtime, cek-python, cek-hw

Key paths: `README.md`, `CORE/`, `META/`, `diagrams/`, `PROPOSALS/`, `KILL-CRITERIA.md`, `CHARTER.md`.

No source entry points, tests, or configs exist in this repository. That is the intended public surface, not an accident.

---

## Accepted residual risks

Unchanged from [`COMPLETENESS.md`](../COMPLETENESS.md):

- Imperfect external undo
- Malicious grantor
- L7 bugs under a valid Cap
- Profile author error (Baseline fallback)

Plus documentation residual:

- Sibling runtimes evolve faster than this charter. The map names them; it does not freeze their crate layouts.
- `docs/` restates CORE in compressed form. If a sentence here and CORE diverge, **CORE wins**.

---

## Quality gate (this pass)

- [x] Core idea graspable in under 60 seconds from [00](00-mental-model.md) and the README portal
- [x] Ownership table unambiguous and contains negative space — [01](01-architecture-and-ownership.md)
- [x] Axioms are absolute and appear early — README and [00](00-mental-model.md)
- [x] Diagrams accurate to CORE + ownership table — `diagrams/00-*.mmd`
- [x] Examples traceable: canonical story CORE/13, scenarios CORE/23, sibling commands from live READMEs
- [x] Walkthrough copy-pasteable as a design checklist; includes authority refusal + reverse failure
- [x] Fragmentation surfaced (implementations, CORE 25–27 vs PROPOSALS)
- [x] Residual confusion targeted at zero for a new contributor’s first five minutes
- [x] Voice is precise; this spine avoids “consider / might / feel free”

---

## Next

[`INDEX.md`](../INDEX.md) · [`COMPLETENESS.md`](../COMPLETENESS.md) · [`CHARTER.md`](../CHARTER.md) · [`PROPOSALS/`](../PROPOSALS/)
