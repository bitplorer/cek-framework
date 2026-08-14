# CORE 15 — Bootstrap root (hardened)

## Problem

Every Cap system needs an origin of authority.  
If left implicit, bootstrap becomes ambient power and destroys A1/A7.

## Rule

**Bootstrap root** is allowed only as:

- **Host-side**,  
- **explicit**,  
- **minimal**,  
- **documented**,  
- and **not available to Peers** as a general API.

## Minimal means

Bootstrap may only:

1. Mint the first Caps required to run the system, and/or  
2. Open a root Activity under those Caps, and/or  
3. Install policy that governs further minting (including meta-Caps).

Bootstrap must **not**:

- Expose unconstrained “do anything” to application code by default.  
- Allow Peers to call bootstrap mint.  
- Skip lineage for subsequent revocable work “because bootstrap was trusted.”  
- Become a permanent second authority path beside Caps.

## Lifecycle of bootstrap

```text
Cold start
  → Host loads bootstrap policy (out of band / config / HSM)
  → Host mints initial Caps under that policy
  → System runs only via Intent under Cap thereafter
  → Bootstrap credentials stay Host-private
```

## Audit

Bootstrap mint events should be distinguishable in lineage or Host audit as **bootstrap-origin** so compromise analysis can start there.

## Amendment

Widening bootstrap surface (e.g. Peer-callable root mint) is a charter-level security change.
