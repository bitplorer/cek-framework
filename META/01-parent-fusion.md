# META 01 — Parent fusion

## Rule

Start from **explicit conceptual parents** only.  
List each parent’s irreducible contribution.  
Fuse into **one** law.  
Do not keep two parallel models.  
Do not admit a silent third parent.

## Why

Languages and frameworks often “borrow ideas” without stating which idea is load-bearing.  
That produces duplicate concepts (two kinds of effect, two kinds of permission, two lifecycles).

Fusion forces a single answer to each intention.

## Method steps

1. **Name the parents** — concrete systems or papers, not vibes.  
2. **Extract irreducible contributions** — only what the child cannot lose.  
3. **Drop parent-local detail** — APIs, file layout, brand words, wire quirks.  
4. **Resolve collisions** — when both parents name related ideas, pick one intention and one name.  
5. **Record the fusion map** — parent contribution → core concept.  
6. **Forbid silent parents** — new influence on L0–L2 requires charter amendment.

## Worked fusion (CEK)

| Parent | Irreducible contribution | Not carried as-is |
|--------|--------------------------|-------------------|
| **ux-channel** | Sealed ask under portable authority; ordered outward changes only; Host decides / Peer carries out; permanent interop baseline; correlation is not authority; fail closed on authority checks | Product Channel façade, specific op catalogs, binary upgrade formats |
| **Cordis** | Bounded composition with lifetime; mediated visible world; declared requirements; structural restriction; caused change is reversible on end | TypeScript API shape, plugin brand, event bus as authority |

### Fusion map

| Intention | Dominant parent insight | Core concept |
|-----------|-------------------------|--------------|
| Ask | ux-channel Intent | **Intent** |
| Allow | ux-channel Cap + Cordis mediated access | **Cap** (+ Context mediation) |
| Carry out | ux-channel Ops | **Ops** / **apply** |
| Bound | Cordis Fiber/Context/inject/isolate | **Activity** / **Context** / **inject** / **limit** / **isolate** / **part** |
| Remember/undo | Cordis effect disposables + accountability | **lineage** / **reverse** |
| Correlate | ux-channel flow-as-correlation-only | **trace** |
| Permanence | ux-channel classic floor | **Baseline** |
| Negotiate apply ability | ux-channel hello/project | **profile** |

## Anti-patterns

- “Also inspired by X” without updating the fusion map.  
- Keeping both parent names for the same job (e.g. Fiber and Activity).  
- Importing a parent’s ambient power model under a new label.

## Amendment

Adding or replacing a parent that changes L0–L2 requires charter amendment and a new fusion map.
