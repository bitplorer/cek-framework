# META 02 — Intention partition

## Rule

Define a **closed set of intentions** before features.  
Every kernel concept maps to **exactly one** intention, or to a single declared orthogonal concern.

## Why

Open-ended feature lists produce overlapping words (“run”, “flow”, “execute”, “session”) that collapse authority, correlation, and lifetime into one mush.

Intentions force design questions:

- Is this an *ask*?  
- Is this *permission*?  
- Is this *carrying out change*?  
- Is this *bounding work*?  
- Is this *remembering/undoing*?  
- Or is it only *grouping* asks?

## CEK intention set (closed)

| Intention | Question | Kernel concepts |
|-----------|----------|-----------------|
| **Ask** | What change is requested? | Intent, submit |
| **Allow** | Is that ask permitted? | Cap, mint |
| **Carry out** | What ordered changes may leave the system? | Ops, apply, Result |
| **Bound** | What work is alive and what ends with it? | Activity, Context, inject, limit, isolate, part |
| **Remember / undo** | What was caused under authority and how is it undone? | lineage, reverse |
| **Correlate only** (orthogonal) | Which asks belong to one multi-step effort? | trace |

No seventh intention may be added without amending this meta-rule and the core vocabulary together.

## Mapping discipline

For each proposed concept:

1. State the intention in one sentence.  
2. Assign one cell in the table.  
3. If it needs two cells, split the concept.  
4. If it needs zero cells, it is not kernel (move to driver, policy, or app).

## Orthogonal concern: correlation

**trace** is not a sixth way to change the world.  
It does not ask, allow, carry out, bound, or undo.  
It only groups Intents that already obey the other intentions.

Treating correlation as authority or execution is a hard reject (see META/09).

## Test

If removing a concept does not remove an intention’s coverage, the concept was redundant.  
If an intention has no concept, the core is incomplete.
