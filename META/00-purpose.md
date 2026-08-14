# META 00 — Purpose of the meta-framework

## Definition

The **meta-framework** is the method used to:

1. Derive a coherent capability-and-effect language core.  
2. Decide what belongs in that core versus outside it.  
3. Name concepts so they remain stable for decades.  
4. Accept or reject future changes without silent drift.

It is **not** the language itself.  
The language core is the *product* of this method (see `CORE/`).

## Why a meta-framework exists

Without an explicit method:

- Features accumulate beside the law instead of under it.  
- Names multiply (synonyms, metaphors, wire names treated as concepts).  
- Authority, correlation, and execution blur.  
- “Temporary” escapes become permanent ambient power.

The meta-framework exists so every design choice is **justified, classified, and reversible only by explicit amendment**.

## Success criteria

A design produced under this meta-framework must:

- Map every kernel concept to a declared intention (or to the single orthogonal concern *correlation*).  
- Satisfy a closed axiom set.  
- Use one official name per concept.  
- Place every mechanism in a layer that does not invert dependencies.  
- Separate *decide* from *carry out*.  
- Require allow → bound → record → reverse for world-changing work.  
- Preserve a permanent Baseline.  
- Reject known drift patterns by name.  
- Be explainable in short canonical sentences using only frozen vocabulary.

## Scope boundary

| In meta-framework scope | Out of scope |
|-------------------------|--------------|
| How to fuse parents | Concrete crypto algorithms |
| How to partition intentions | JSON field paths |
| How to lock axioms | UI widget catalogs |
| How to name and reject names | Benchmark numbers |
| How to layer and change | Hosting topology |

## Relationship to the core

```text
META (method)  ──produces / governs──►  CORE (law)
CORE  ──must remain explainable by──►  META tests
```

If the core cannot be re-derived from the meta-framework, the core has drifted or the meta-framework is incomplete. Both are defects.
