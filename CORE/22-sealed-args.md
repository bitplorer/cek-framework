# CORE 22 — Sealed arguments

## Problem

If the caller can change any argument after permission is granted, Cap becomes theater (confused deputy / bait-and-switch).

## Rule

A Cap binds the **sealed** portion of arguments.  
The Host verifies that the Intent’s sealed args match the Cap bind before dispatch.

## Conceptual split

| Kind | Trust | Use |
|------|-------|-----|
| **Sealed args** | Bound by Cap; caller cannot alter without invalidating Cap | Identifiers, fixed quantities, targets the grantor already approved |
| **Open / form args** | Not bound by Cap; filled by caller | Progressive enhancement, optional fields Host re-validates from truth |

Hosts **reload authoritative state** from their store for magnitudes, balances, roles, and other truth — they do not trust caller-supplied “full world state.”

## Failures

Mismatch of sealed args → Cap verify failure → refuse (no side-effects).

## Relation to axioms

Supports A1 (Cap-only truth) and the sealed-args threat row in [14](14-security-model.md).
