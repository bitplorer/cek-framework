# CORE 08 — Cap

## Meaning

A **Cap** is permission to **submit** a specific class of **Intent**.

It is the sole authority object at the kernel boundary (axiom A1).

## Conceptual binds

A Cap conceptually binds at least:

- the **action** (what ask is allowed),  
- integrity of **sealed arguments** (what may not be altered by the caller),  
- a **time window** or equivalent validity constraint,  

and may bind:

- **subject** (who),  
- **scopes** (qualitative limits),  
- **single-use** constraints.

Exact encoding is implementation. The binds are conceptual law.

## mint

**mint** creates a Cap.  
Minting is a Host-side (or higher Cap-gated) privilege — not a Peer right (axiom A7).

## verify

Before dispatch, the Host verifies the Cap against the Intent.  
Failure → refuse (axiom A5).

## Attenuation

Caps and Context restrictions may be **limited** only by narrowing:

- fewer actions,  
- tighter sealed args,  
- shorter validity,  
- fewer scopes,  
- fewer visible Context surfaces.

Widening is forbidden (axiom A8).

## Meta-Caps

Caps that mint, limit, or revoke other Caps are themselves Cap-gated and lineage-tracked.  
They do not create ambient root power outside bootstrap policy.

## Cap vs trace vs Activity

| Concept | Grants permission? | Groups steps? | Owns lifetime undo? |
|---------|--------------------|---------------|---------------------|
| Cap | Yes | No | Via lineage when revocable |
| trace | No | Yes | No |
| Activity | No | No | Yes (reverse lineage on end) |

## See also

- [22-sealed-args.md](22-sealed-args.md)
- [14-security-model.md](14-security-model.md)
