# CORE 05 — Layers

```text
L0  Law         axioms + Baseline
L1  Kernels     Host · Peer
L2  Bound work  Activity · Context · inject · limit · isolate · lineage · reverse · part
L3  Correlate   trace
L4  Negotiate   profile
L5  Drivers     domain Ops
L6  Policy      optional
L7  Application product logic
```

## Layer responsibilities

### L0 Law
Defines what is true regardless of implementation: axioms, Baseline shape, Cap-only / Ops-only.

### L1 Kernels
Host and Peer mechanical duties. No domain semantics beyond verify/dispatch/apply.

### L2 Bound work
Lifetime, visibility, composition units, cause trail, undo.

### L3 Correlate
trace only. No authority, no execute.

### L4 Negotiate
profile declares apply ability; Host projects Ops the Peer can apply, including Baseline fallback.

### L5 Drivers
Meaning of domain Ops (e.g. interface morph, agent log, device set). Drivers do not mint root Caps.

### L6 Policy
Optional quantitative grades, meta-Caps, compensation synthesis, distributed agreement on lineage — all *on top of* L0–L2.

### L7 Application
Handlers, stores, product Activities, UX. Must submit Intents under Caps for shared-world change.

## Invariants

- Lower never depends on higher.  
- L5–L7 replaceable without changing L0–L2 meaning.  
- L6 cannot bypass Cap verify or Ops-only emission.
