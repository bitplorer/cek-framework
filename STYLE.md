# Documentation style (clarity and consistency)

## Voice

- Prefer short sentences and tables.  
- Prefer **canonical speech** vocabulary only for kernel ideas.  
- Prefer “must / must not / may” for rules; avoid soft “should” when an axiom is at stake.

## Terms

| Use | Do not use (for the same job) |
|-----|-------------------------------|
| Intent | command, request (as kernel noun) |
| Cap | token, permission (as kernel noun) |
| Ops | effects (as emission list) |
| Activity | Fiber, session, plugin |
| Baseline | Floor, legacy (as kernel noun) |
| trace | flow, run, thread, group (as correlation concept) |
| lineage | history, record (as cause trail) |
| part | plugin (ambient load) |
| Host / Peer | server / client (as role names) |

Rejected names may appear only when **explaining rejection** or parent ancestry.

## Concept vs encoding

- Framework docs name **concepts** (trace, Cap, Activity).  
- Do not promote field paths or encodings into the intention table.  
- Implementations may use ids and tokens; that does not add kernel nouns.

## Document shape

Preferred section order for CORE docs:

1. Meaning / rule  
2. What it is not  
3. Relations to other concepts  
4. Axiom links  
5. See also (optional)

## Cross-links

- Prefer relative links: `CORE/03-axioms.md`, `../META/SUMMARY.md`.  
- SUMMARY and INDEX are the navigation hubs.  
- PROPOSALS must say **not frozen** when referenced from frozen docs.

## Status labels

| Label | Meaning |
|-------|---------|
| **Frozen** | META, CORE, STABILITY, CHARTER vocabulary/axioms |
| **Not frozen** | PROPOSALS until adopted |
| **Informative** | CHOICES ancestry notes, examples in scenarios |

## One-line cores (keep identical everywhere)

**Meta:** Fuse explicit parents → partition by intention → lock axioms → name by job → layer strictly → split decide/carry out → require allow/bound/record/reverse → protect Baseline → reject drift → test by canonical speech.

**Core:** Mint Cap → submit Intent → apply Ops → bound in Activity → record lineage → reverse on end → group with trace → keep Baseline.
