# CORE 06 — Host and Peer

## L1 kernel set (closed)

L1 has **exactly two** kernels (roles):

| Kernel | Role | Duty summary |
|--------|------|--------------|
| **Host** | Decide | Mint/verify Cap; dispatch; lineage; project; Result |
| **Peer** | Carry out | Apply Ops under profile; never mint root Caps; never invent truth |

There is **no third L1 kernel**.  
Caller, bootstrap, lineage store, recovery Cap, profile, transport, and conformance harness are **not** kernels.

## Host duties

Ordered conceptual pipeline for each ask (fail closed; no shared-world side-effects before the gate):

1. **Verify** Cap against the Intent (integrity, expiry, action bind, sealed args, optional subject/scopes). Refuse → no mutate Ops.  
2. **Consume** single-use constraints and check optional **idempotency bind** before side-effects when required; required store unavailable → **refuse**.  
3. **Dispatch** the action only after verify (and after consume/bind checks).  
4. **Record lineage** when the Cap is revocable or the Activity is endable (authorized set + reverse plan).  
5. **Project** Ops to what the Peer’s **profile** can apply, falling back to **Baseline** forms when needed.  
6. Return a **Result** containing ordered **Ops** or an error (authority refusal distinct from business miss when possible).

Additionally: **Mint** Caps under policy (Host-side privilege, including bootstrap and recovery Caps).

## Peer duties

1. **Apply** Ops in order under its profile.  
2. Ignore unknown correlation/meta that is not required for Baseline.  
3. Handle unknown Ops per profile policy (ignore, soft-fail, or reject in strict profiles) without crashing the kernel.  
4. Optionally report an **apply receipt** (landed vs failed); receipts are not Caps.  
5. **Must not** mint root Caps.  
6. **Must not** invent business truth (e.g. rewrite sealed outcomes).

## Boundary

```text
Intent + Cap  ──►  Host  ──►  Result + Ops  ──►  Peer
                     │
                     └── lineage / reverse (Host-owned)
```

Truth and permission are Host-side.  
World mutation at the boundary is Peer-side apply of Ops (and Host-side lineage accounting).

## Multiplicity

Many **implementations** of Host and of Peer may exist (languages, processes, hardware).  
Multiplicity does **not** add roles: each decide boundary is still a Host; each apply boundary is still a Peer.

The role law does not require a single process or a browser/server topology.  
A process may embed both roles as separate boundaries; mint must not live inside pure apply.

## Cross-Host Caps

A Cap minted under one Host’s policy is not automatically authority on another Host.  
Cross-Host acceptance requires **explicit** shared verify policy (keys, trust domain, dual-speak window). Default is separate trust domains.
