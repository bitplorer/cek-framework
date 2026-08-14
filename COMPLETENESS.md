# Completeness

Conceptual charter coverage. **Complete** = law stated, not implementation shipped.

## Covered

| Area | Where |
|------|--------|
| Meta method | META/00–10 |
| Axioms, vocabulary, layers, roles | CORE/03–07 |
| Cap, Activity, lineage, trace, Baseline | CORE/08–11 |
| Change law, speech | CORE/12–13 |
| Security, bootstrap, versioning, extensibility | CORE/14–17 |
| Invariants, conformance, errors | CORE/18–20 |
| Intent/Result/Ops, sealed args, scenarios | CORE/21–23 |
| Moving parts / corner defaults | CORE/24 |
| Quickstart, kill criteria | CORE/QUICKSTART, KILL-CRITERIA |
| Manifest, lineage↔receipt norm | CORE/11, CORE/09 |
| Landed set / receipts (explicit) | CORE/25 |
| Idempotency bind (optional explicit) | CORE/26 |
| Recovery Cap (explicit) | CORE/27 |
| Stability, glossary, style, choices | root docs |
| Diagrams | diagrams/ |
| Optional extensions | PROPOSALS/ (unfrozen) |

## Out of scope (not gaps)

Cap crypto · wire field paths · full domain Op catalogs · performance SLOs · IFC-in-Baseline · source code

## Accepted residual risks

Imperfect external undo (mark/compensate) · malicious grantor · L7 bugs under valid Cap · profile author error (Baseline fallback)

## Verdict

META + CORE conceptual freeze is **complete**. Further work = implementation, published vectors, optional PROPOSALS adoption.
