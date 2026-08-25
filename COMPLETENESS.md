# Completeness

Conceptual charter coverage. **Complete** = law stated, not implementation shipped.

Reader path (map, not a second law): [`docs/`](docs/).

## Covered

| Area | Where |
|------|--------|
| Reader spine (mental model, ownership, happy path, reality) | docs/00–03 |
| Developer glance + problem framing | README |
| Concept explainers (boxes, is/is-not) | CONCEPTS.md |
| Meta method | META/00–10 |
| Axioms, vocabulary, layers, roles | CORE/03–07 |
| Cap lifecycle, Activity, lineage, trace, Baseline | CORE/08–11 |
| Host/Peer L1 set, ordered pipeline, cross-Host Caps | CORE/06 |
| Change law, speech | CORE/12–13 |
| Security, bootstrap, versioning, extensibility | CORE/14–17 |
| Invariants, conformance, errors | CORE/18–20 |
| Intent/Result/Ops, sealed args, scenarios | CORE/21–23 |
| Corners, receipts, idempotency, recovery Cap | CORE/24–27 |
| Framework name; rejected language aliases | CHOICES, CORE/00 |
| Quickstart, kill criteria | CORE/QUICKSTART, KILL-CRITERIA |
| Glossary, stability, style, charter | root docs |
| Diagrams | diagrams/ (including 00 mental model, ownership, primary flow) |
| Optional extensions | PROPOSALS/ (unfrozen) |

## Out of scope (not gaps)

Cap crypto · wire field paths · domain Op catalogs · SLOs · source code · languages · crates · CI · isolation  
→ [cek-runtime](https://github.com/bitplorer/cek-runtime) · [cek-python](https://github.com/bitplorer/cek-python) · [cek-hw](https://github.com/bitplorer/cek-hw) (L5 apply)

## Dual path (surfaced, not hidden)

CORE 25–27 freeze conceptual rules for receipts, idempotency bind, and recovery Cap (optional for Baseline). PROPOSALS P1/P4 retain adoption rationale. Remaining unfrozen: P2, P3, P5–P8.  
→ [docs/03-current-reality.md](docs/03-current-reality.md)

## Accepted residual risks

Imperfect external undo · malicious grantor · L7 bugs under valid Cap · profile author error (Baseline fallback)

## Verdict

META + CORE conceptual freeze is **complete** for law.  
Further work = published vectors, optional PROPOSALS, and implementation that claims alignment without amending this charter.
