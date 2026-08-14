# META 07 — Accountability loop

## Rule

Whatever can change the shared world must be:

1. **Allowed** — under a Cap  
2. **Bounded** — inside an Activity (lifetime/scope) when composition/undo applies  
3. **Recorded** — in lineage when Cap is revocable or Activity is endable  
4. **Reversible** — via reverse (inverse or compensation)

**trace** may group steps; it must not replace any of the four.

## Why

Security systems often stop at authentication.  
Composition systems often stop at lifecycle.  
UI protocols often stop at messages.

The meta-framework requires the full loop so “hot unload”, “revoke”, and “multi-step abandon” remain defined.

## Loop diagram (conceptual)

```text
Allow (Cap)
   ↓
Ask (Intent)
   ↓
Carry out (Ops) ──► Record (lineage)
   ↓
Bound (Activity ends) ──► Reverse (lineage)
```

Optional parallel:

```text
trace ── groups multiple Allow/Ask cycles ── never substitutes for Cap or lineage
```

## Minimum vs enriched

| Situation | Minimum loop |
|-----------|----------------|
| Single irrevocable fire-and-forget under policy | Cap + Intent + Ops; lineage policy may be narrower if explicitly non-revocable and non-endable |
| Revocable Cap or endable Activity | Full record + reverse |
| Multi-step product effort | Full loop per step + shared trace |

Designs that skip record/reverse for “convenience” on revocable paths violate the meta-framework.

## Compensation

When a true inverse does not exist in the outside world, **reverse** still has a job: submit compensating asks under a recovery Cap, or mark non-reversible with audit. Silent success is forbidden.
