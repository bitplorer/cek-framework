# CORE 17 — Extensibility (flexible without weakening)

## Principle

**Extend upward and outward; do not tunnel through the law.**

Flexibility lives in L4–L7 and in additive profiles.  
Security and stability live in L0–L2.

## Extension points (allowed)

| Extension | Layer | Constraint |
|-----------|-------|------------|
| New domain Ops | L5 | Projectable or ignorable for Baseline Peers |
| New Peer surfaces (UI, agent, device) | L5 | Still apply Ops only |
| Richer profiles | L4 | Negotiate apply ability only |
| Grades, budgets, quotas | L6 | Enforced before dispatch; cannot replace Cap |
| Meta-Caps / policy engines | L6 | Cap-gated; lineage-tracked |
| Compensation strategies | L6/L2 | Must still reverse or mark non-reversible |
| Application Activities and parts | L7 | Cap-gated composition |
| Optional proofs over lineage | L6 | Separate key purpose from Cap material |

## Extension anti-patterns (forbidden)

| Pattern | Why blocked |
|---------|-------------|
| “Trusted mode” skipping Cap | Breaks A1 |
| Side door emit outside Ops | Breaks A2 |
| Using trace as session auth | Breaks A6 |
| Peer self-grant root Cap | Breaks A7 |
| Limit that grants more than parent held | Breaks A8 |
| Plugin load without Cap | Breaks A9 |
| Second official name for Cap/Intent | Breaks A10 |

## Compatibility pattern for new Ops

```text
1. Define Op in a domain namespace
2. Document Baseline lowering (equivalent classic Ops or safe no-op)
3. Advertise in profile
4. Host projects intersection
5. Add conformance vectors for rich + baseline paths
```

## Multi-Hop and multi-Peer

Extending to more Peers does not change the law:

- Each apply boundary is still Peer.  
- Each decide boundary is still Host (or Host-delegated under Cap).  
- Lineage remains Cap/Activity-accountable across hops if revocation spans them (L6 may add distributed agreement; it cannot drop accountability).

## Deterministic projection (hardening)

Given the same Intent outcome, same profile, and same projection rules, Host projection to Ops should be **deterministic**.  
Non-determinism belongs in L7 generators *before* commit to Result, not in silent apply divergence.
