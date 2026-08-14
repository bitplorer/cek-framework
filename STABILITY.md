# Language stability guarantees

CEK aims at **decades-stable conceptual law**, comparable to the stability expectations of a programming language’s core semantics—not a rapidly churning application framework.

## Guarantees

| Guarantee | Statement |
|-----------|-----------|
| **Vocabulary stability** | Primary kernel names do not rename. |
| **Baseline interop** | Correct old Baseline Peers keep working with correct Hosts that also speak richer profiles. |
| **Semantic honesty** | Same name keeps the same intention; meaning shifts require major law version. |
| **Additive extension** | New power prefers profiles and domain Ops with Baseline lowering. |
| **Explicit failure** | Authority path fails closed; no “best effort allow.” |
| **Accountable end** | Ending Activities and revoking Caps have a defined reverse story. |
| **Documented change** | Kernel changes follow CHARTER amendment + CORE/12. |

## Non-guarantees (honest scope)

| Non-guarantee | Note |
|---------------|------|
| Eternal domain Op catalogs | Domains evolve at L5 |
| Single implementation forever | Multiple Host/Peer implementations allowed |
| Perfect undo of the external world | Compensation and non-reversible marks exist |
| Transport or crypto agility details | Conceptual binds matter; algorithms may evolve |
| Absence of L7 bugs | App handlers can still be wrong *under* Caps |

## Flexibility without fragility

Flexibility is achieved by:

- **profile** negotiation,  
- **domain Ops**,  
- **optional L6 policy**,  
- **parts** and **Activities** as composition,  

not by relaxing A1–A10.

## Review cadence (recommended)

- Kernel/charter changes: rare, recorded, dual-speak when needed.  
- L5 drivers: normal evolution with conformance for lowering.  
- L7 products: free within Cap law.

## Alignment boundary

Claiming CEK alignment requires not violating [KILL-CRITERIA.md](KILL-CRITERIA.md) and satisfying required conformance families in [CORE/19-conformance.md](CORE/19-conformance.md).
