# CORE 06 — Host and Peer

## Host duties

1. **Mint** Caps under policy (Host-side privilege).  
2. **Verify** Cap before acting on an Intent (signature/integrity, expiry, action bind, sealed args bind, optional subject/scopes).  
3. **Consume single-use** constraints before side-effects when policy requires; if the required store is unavailable → **refuse** (fail closed).  
4. **Dispatch** the action only after verify.  
5. **Record lineage** when the Cap is revocable or the Activity is endable.  
6. Return a **Result** containing ordered **Ops** or an error.  
7. **Project** Ops to what the Peer’s **profile** can apply, falling back to **Baseline** forms when needed.

## Peer duties

1. **Apply** Ops in order under its profile.  
2. Ignore unknown correlation/meta that is not required for Baseline.  
3. Handle unknown Ops per profile policy (ignore, soft-fail, or reject in strict profiles) without crashing the kernel.  
4. **Must not** mint root Caps.  
5. **Must not** invent business truth (e.g. rewrite sealed outcomes).

## Boundary

```text
Intent + Cap  ──►  Host  ──►  Result + Ops  ──►  Peer
```

Truth and permission are Host-side.  
World mutation at the boundary is Peer-side apply of Ops (and Host-side lineage accounting).

## Multiplicity

Many Hosts and Peers may exist.  
The role law does not require a single process or a browser/server topology.
