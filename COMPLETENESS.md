# Completeness

Conceptual charter coverage. **Complete** = law stated, not implementation shipped.

## Covered

| Area | Where |
|------|--------|
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
| Diagrams | diagrams/ |
| Optional extensions | PROPOSALS/ (unfrozen) |

## Out of scope (not gaps)

Cap crypto · wire field paths · domain Op catalogs · SLOs · source code · languages · crates · CI · isolation  
→ [cek-runtime](https://github.com/bitplorer/cek-runtime)

## Accepted residual risks

Imperfect external undo · malicious grantor · L7 bugs under valid Cap · profile author error (Baseline fallback)

## Verdict

META + CORE conceptual freeze is **complete** for law.  
Further work = published vectors, optional PROPOSALS, and implementation that claims alignment without amending this charter.
