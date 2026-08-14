# Completeness

Conceptual charter coverage. **Complete** = law stated, not implementation shipped.

## Covered

| Area | Where |
|------|--------|
| Meta method | META/00–10 |
| Axioms, vocabulary, layers, roles | CORE/03–07 |
| Cap (binds + conceptual lifecycle), Activity, lineage, trace, Baseline | CORE/08–11 |
| Host/Peer closed L1 set, ordered Host pipeline, multiplicity, cross-Host Caps | CORE/06 |
| Change law, speech | CORE/12–13 |
| Security, bootstrap, versioning, extensibility | CORE/14–17 |
| Invariants, conformance, errors | CORE/18–20 |
| Intent/Result/Ops, sealed args, scenarios | CORE/21–23 |
| Moving parts / corner defaults | CORE/24 |
| Landed set / receipts | CORE/25 |
| Idempotency bind (optional explicit) | CORE/26 |
| Recovery Cap | CORE/27 |
| Framework name = CEK; rejected language aliases | CHOICES, CORE/00 |
| Quickstart, kill criteria | CORE/QUICKSTART, KILL-CRITERIA |
| Stability, glossary, style, choices | root docs |
| Diagrams | diagrams/ |
| Optional extensions | PROPOSALS/ (unfrozen) |

## Out of scope (not gaps)

Cap crypto · wire field paths · full domain Op catalogs · performance SLOs · IFC-in-Baseline · source code · implementation language · crate layout · CI · process/WASM isolation · Host/Peer SDK packaging

Those belong in a separate **implementation framework**, not in META/CORE.

## Accepted residual risks

Imperfect external undo (mark/compensate) · malicious grantor · L7 bugs under valid Cap · profile author error (Baseline fallback)

## Verdict

META + CORE conceptual freeze is **complete** for law.  
Further work = published conformance vectors, optional PROPOSALS adoption, and implementation frameworks that claim CEK alignment without amending this charter.
