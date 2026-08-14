# CORE 20 — Errors and concurrency (conceptual)

## Errors

### Principle

Authority failures and apply failures must remain **distinguishable** in Results so callers do not treat “unauthorized” as “soft business miss.”

### Conceptual classes

| Class | Meaning | Typical handling |
|-------|---------|------------------|
| **Authority refusal** | Cap verify failed, single-use replay, store down | Fail closed; no side-effects |
| **Dispatch error** | Action missing, policy deny after verify | No Ops or explicit error Ops only under policy |
| **Apply error** | Peer could not apply some Ops | Profile policy: stop vs continue; report |
| **Reverse error** | Inverse/compensation incomplete | Mark non-reversible; audit; do not claim clean reverse |

Baseline does not require a single error taxonomy encoding; it requires that **authority refusal does not partially apply world changes**.

## Concurrency

### Principle

Multiple Activities and Intents may proceed concurrently.  
The law does not freeze a single global lock; it requires **Cap and lineage accountability per change**.

### Rules

1. **No Cap sharing that violates single-use** — concurrent submit of the same single-use Cap: at most one succeeds consume.  
2. **Lineage is per cause** — concurrent Activities do not merge lineage unless an explicit L6 policy defines joint reverse.  
3. **Context mediation is per Activity** — isolate/limit apply to that Activity’s view.  
4. **trace** may span concurrent Intents; still grants no power.  
5. **Deterministic apply order** — Ops in one Result apply in listed order; cross-Result ordering is app/Host scheduling, not ambient Peer reordering of a single Result.

### Isolation vs performance

Stronger isolation (serial Activities, stricter budgets) is L6/L7 policy.  
Weaker isolation must not become Cap bypass.
