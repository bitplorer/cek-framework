# META 05 — Layer law

## Rule

Order the system so **lower layers never depend on upper layers**.  
Place each mechanism in the correct layer.  
Protect bottom layers hardest.

## Why

Without layers:

- Policy leaks into kernels.  
- Drivers redefine authority.  
- App conveniences become ambient power.  
- “Just this once” sits beside the law instead of above it.

## Layer model (CEK)

```text
L0  Law         axioms + Baseline
L1  Kernels     Host · Peer
L2  Bound work  Activity · Context · inject · limit · isolate · lineage · reverse · part
L3  Correlate   trace
L4  Negotiate   profile
L5  Drivers     domain Ops
L6  Policy      optional grades, meta-Caps, compensation synthesis, …
L7  Application handlers, stores, product logic
```

## Placement tests

| Question | Layer |
|----------|-------|
| Does this redefine what counts as authority or legal effect? | L0 |
| Is this verify-vs-apply machinery? | L1 |
| Is this lifetime, visibility, or undo of caused change? | L2 |
| Is this only grouping asks? | L3 |
| Is this negotiating apply ability without new authority? | L4 |
| Is this a domain meaning of an Op? | L5 |
| Is this optional stricter policy on top of the law? | L6 |
| Is this product-specific? | L7 |

## Dependency rule

- L*n* may depend on L*0…n-1* only.  
- L5–L7 may be swapped or replaced without changing L0–L2 meaning.  
- L6 may not punch a hole through L0–L1 (e.g. cannot create ambient Cap bypass).

## Change severity by layer

| Layers | Severity |
|--------|----------|
| L0–L2 | Charter-level |
| L3–L4 | Careful; must preserve axiom 6 and Baseline |
| L5–L7 | Normal evolution if axioms hold |
