# CORE 19 — Conformance requirements

## Purpose

Narrative docs do not define correctness alone.  
**Conformance vectors and behaviors** do.

## Required behavior families

Any claim of **CEK-compatible** or **CEK-aligned** must demonstrate all rows below.

| Family | Must demonstrate |
|--------|------------------|
| Cap verify | Success; reject bad integrity; reject action mismatch; reject sealed-arg mismatch; reject expired |
| Single-use | Consume-before-effects; second use fails; store down fails closed when required |
| Baseline apply | Peer with minimal profile can apply projected classic Ops |
| **Baseline lowering** | Rich internal outcome is projectable to classic Ops a Baseline Peer can apply |
| Unknown meta | Ignored without failure on Baseline path |
| Unknown Ops | Policy-defined ignore/soft-fail/strict-reject; no kernel crash |
| Lineage | Record on required path (revocable Cap or endable Activity) |
| **Reverse on end** | Activity end runs reverse; failed reverse is not silent success (mark non-reversible) |
| Trace | Two Intents share trace; neither gains authority from it |
| Attenuation | Limited Cap cannot exercise removed rights |
| Peer limits | Peer cannot mint root Cap in conformance harness |

**Baseline lowering** and **Reverse on end** are mandatory for compatibility claims (not optional theater).

## Vector discipline

- Vectors are versioned alongside law version.  
- Major law version adds a new vector suite; Baseline suite remains green during dual-speak.  
- Implementations claim conformance only to published suites.  
- Kill criteria: [`../KILL-CRITERIA.md`](../KILL-CRITERIA.md).

## Optional high-assurance families

| Family | When |
|--------|------|
| Idempotent submit | Production profiles (recommended) |
| Apply receipt into lineage | Multi-Peer / high-assurance profiles |
| Hash-chained lineage | Audit-focused deployments |

See [`../PROPOSALS/radical-minimal-downside.md`](../PROPOSALS/radical-minimal-downside.md).

## Non-goals of conformance

- Performance SLOs  
- Specific crypto suite  
- Full IFC proofs  
- Product UX  
