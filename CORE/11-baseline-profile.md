# CORE 11 — Baseline and profile

## Baseline

**Baseline** is the permanent shared contract every correct Host/Peer pair supports:

- Intent under Cap  
- Result with ordered Ops  
- Host verifies; Peer applies  
- Classic apply ability sufficient for interop  

Baseline is a **concept of permanence**, not a runtime object you “open” like an Activity.

### Permanence rule

Improvements add power *above* Baseline or introduce an explicit major version of meaning.  
They do not silently redefine Baseline (axiom A4).

## profile

A **profile** declares what a Peer can **apply**.

- Host uses profile to project Ops the Peer understands.  
- Missing or limited profile → Baseline projection.  
- Profile never grants Cap authority.

## Negotiation shape (conceptual)

```text
Peer declares profile
Host projects Ops ⊆ peer ability ∪ Baseline fallback
Peer applies
```

## Baseline manifest (conceptual)

Hosts and Peers may exchange a small **manifest** of compatibility facts. Encoding is free; concepts are fixed:

| Element | Purpose |
|---------|---------|
| **Law generation** | Which CEK law generation / Baseline generation is spoken |
| **Profiles supported** | Apply-ability names the party can use |
| **Fail-closed behaviors** | Confirms once-store-down and Cap-fail refuse |
| **Optional families** | e.g. receipts, idempotency (if any) |

Rules:

- Manifest never grants Cap authority.  
- Missing manifest → assume Baseline-only Peer.  
- Manifest drift without dual-speak is a compatibility defect.

## See also

- [16-versioning.md](16-versioning.md)
- [19-conformance.md](19-conformance.md)
