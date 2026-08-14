# CORE 23 — Interop scenarios

Illustrative scenarios. All must obey axioms.

## S1 — Single Host, single Peer (classic)

1. Host mints Cap.  
2. Caller submits Intent under Cap.  
3. Host verifies, records lineage if required, returns Result with Ops.  
4. Peer applies Ops.  

Baseline sufficient.

## S2 — Activity-scoped multi-step work

1. Open Activity (Cap-gated); inject requirements; optional limit/isolate.  
2. Several Intents under (possibly different) Caps; optional shared **trace**.  
3. End Activity → reverse lineage.  

Trace groups steps; each step still needs Cap.

## S3 — Part load / unload

1. Load **part** under Cap into Activity.  
2. Part’s work produces lineage under that Activity.  
3. Unload part / end Activity → reverse.

## S4 — Rich Peer vs Baseline Peer

1. Rich Peer declares profile.  
2. Host projects rich Ops when possible.  
3. Baseline Peer omits profile → classic Ops only.  
Both remain correct.

## S5 — Authority refusal

1. Invalid or replayed Cap.  
2. Host fails closed; no mutate Ops applied.  
3. Result signals authority refusal.

## S6 — Partial apply

1. Result contains Ops.  
2. Peer applies some, fails some.  
3. Policy (profile) defines stop vs continue; optional receipt (PROPOSALS) can report back into lineage.

## S7 — Irreversible external effect

1. Mutate Op has no true inverse.  
2. Reverse uses compensation Intent under recovery Cap, or marks non-reversible with audit.  
3. Never silent “fully reversed.”

## S8 — Bootstrap then steady state

1. Host bootstrap mints initial Caps only.  
2. Thereafter all shared-world change is Intent under Cap.  
3. Peer never calls bootstrap mint.
