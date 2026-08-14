# CORE 10 — Trace

## Meaning

A **trace** correlates related **Intents** as one multi-step effort.

It answers: *which asks belong together?*  
It does **not** answer: *who is allowed?* or *what may be applied?* or *what must be undone?*

## Laws

- Trace is **not authority** (axiom A6).  
- Each step remains **Intent under Cap**.  
- Ending a multi-step effort still **reverse**s **lineage** under the relevant Activities/Caps — the trace does not undo by itself.  
- Resume of multi-step work uses **fresh Caps** under policy; a trace does not revive expired permission.

## Durable state

Product state for multi-step work lives in application storage (L7).  
The Peer kernel does not become the system of record for business workflows merely because a trace exists.

## Naming note

The concept is **trace**.  
Implementations may assign identifiers to traces; identifiers are not a separate kernel concept.

## See also

- [24-moving-parts-and-corners.md](24-moving-parts-and-corners.md) — defaults when trace is absent or misused
- [08-cap.md](08-cap.md) — permission remains Cap
