# CEK Quickstart — irreducible core only

Read this first. Everything else elaborates.

---

## One line

**Mint Cap → submit Intent → apply Ops → bound in Activity → record lineage → reverse on end → group with trace → keep Baseline.**

---

## Intentions

| Job | Concepts |
|-----|----------|
| Ask | Intent, submit |
| Allow | Cap, mint |
| Carry out | Ops, apply, Result |
| Bound | Activity, Context, inject, limit, isolate, part |
| Remember / undo | lineage, reverse |
| Correlate only | trace |

---

## Axioms (short)

1. Only a verified **Cap** is authority.  
2. Only ordered **Ops** leave the kernel boundary.  
3. Revocable Cap / endable Activity → **lineage**.  
4. **Baseline** never silent-breaks.  
5. Authority path **fails closed**.  
6. **trace** is not authority.  
7. **Peer** does not mint root Caps or invent truth.  
8. **limit** / **isolate** only narrow.  
9. Activity / part load is Cap-gated (or explicit Host bootstrap).  
10. One concept, one name.

---

## Roles

- **Host** — mint/verify Cap, dispatch, lineage, Result with Ops.  
- **Peer** — apply Ops only.

---

## Canonical story

```text
Host mints a Cap.
Caller submits an Intent under that Cap.
Host verifies Cap, records lineage, returns Result with Ops.
Peer applies Ops.

Work is an Activity in a Context.
Related Intents share a trace.
When an Activity ends, reverse its lineage.
Everyone supports the Baseline.
```

---

## Defaults when unsure

| Situation | Do |
|-----------|-----|
| Authority unclear | Refuse |
| Unknown optional meta | Ignore |
| Peer can’t do rich Ops | Lower to Baseline |
| Undo impossible | Mark non-reversible; don’t fake success |
| Multi-step group | trace (still need Cap each step) |
| Partial apply | reverse prefers **landed** Ops if receipt exists |
| Compensation | recovery Cap; else mark non-reversible |

---

## Not CEK if

Ambient allow without Cap · Peer root mint · trace as permission · silent Baseline break · free side-effects outside Ops  

Full list: [`../KILL-CRITERIA.md`](../KILL-CRITERIA.md)

---

## Next

| Depth | Doc |
|-------|-----|
| Law | [SUMMARY.md](SUMMARY.md) |
| Corners | [24-moving-parts-and-corners.md](24-moving-parts-and-corners.md) |
| Security | [14-security-model.md](14-security-model.md) |
| Index | [`../INDEX.md`](../INDEX.md) |
