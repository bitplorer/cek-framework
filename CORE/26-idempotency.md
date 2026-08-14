# CORE 26 — Idempotency bind (optional, recommended)

Safe retries without double cause. **Not required for Baseline.** Recommended for production profiles (PROPOSALS P1).

---

## Meaning

An **idempotency bind** is an optional Cap/Intent claim that identifies one logical ask.

If the Host sees a second submit with the same bind (within policy window) after a completed or in-flight handling, it does **not** create a second lineage cause or second mutate effect.

---

## Rules

1. Bind is checked **after** Cap verify, **before** side-effects (same ordering spirit as single-use).  
2. If the idempotency store is required and **down** → **refuse** (fail closed), consistent with A5.  
3. First successful handling records lineage once; duplicates return the prior Result (or equivalent safe replay of Result) per Host policy.  
4. Bind does **not** replace Cap, once/jti, or trace.  
5. Baseline Peers need not understand the bind; it is Host-side.

---

## Distinct from

| Mechanism | Job |
|-----------|-----|
| Cap | Permission |
| once / single-use | This Cap instance usable once |
| idempotency bind | This logical ask executed once even if Intent is resubmitted |
| trace | Group related steps |

---

## See also

- [08-cap.md](08-cap.md)  
- [24-moving-parts-and-corners.md](24-moving-parts-and-corners.md)  
- [../PROPOSALS/radical-minimal-downside.md](../PROPOSALS/radical-minimal-downside.md) (P1)  
