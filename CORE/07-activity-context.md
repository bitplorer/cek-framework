# CORE 07 — Activity and Context

## Activity

**Activity** is bounded work with a lifetime:

- opens (starts),  
- runs (may submit Intents under Caps),  
- ends (completes, cancels, fails, or is unloaded).

When an Activity ends, the Host **reverse**s its **lineage** under recovery policy.

### Activity is not

- a Cap (it does not by itself allow asks),  
- a trace (it is not merely correlation),  
- the whole application,  
- an OS thread.

### Composition

**part**s load into an Activity under Caps (axiom A9).  
Loading and unloading parts are themselves accountable composition events.

## Context

**Context** is the mediated visible world of an Activity: what services, data surfaces, or coeffects the work may see.

### Context is not

- ambient authority,  
- a substitute for Cap on outward asks,  
- a global bag of unconstrained power.

### inject

**inject** declares what an Activity **requires** from its Context to run.  
Undeclared access fails closed under mediation.

### limit / isolate

- **limit** — restrict what may be seen or done (public restriction verb).  
- **isolate** — separate a Context slice so names/services do not leak across boundaries.  

Both are **monotonic**: they only narrow (axiom A8).

## Relationship

```text
Activity
  └── lives in Context
        ├── inject requirements
        ├── limit / isolate visibility
        └── submits Intents under Caps
              └── contributes to lineage
```
