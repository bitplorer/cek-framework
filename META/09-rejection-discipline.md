# META 09 — Rejection discipline

## Rule

Explicitly reject designs and names that:

- collide with execute, authority, or undo,  
- imply ambient power,  
- are metaphors without a clear job,  
- or create synonym drift.

Rejected items stay rejected unless the meta-framework is amended.

## Rejected name classes (CEK)

| Reject | Reason |
|--------|--------|
| Fiber | Unclear job (not obviously bounded work) |
| Floor | Metaphor without obvious permanence meaning |
| run | Collides with execute; bad correlation name |
| flow | Product/engine collision; historically confused with authority |
| thread | OS collision |
| group / related as concept name | Too vague for multi-step path correlation |
| history / record as cause-trail concept | Generic logging, weak authority link |
| plugin as ambient load | Implies composition without Cap |
| command as Intent | Weaker intention |
| token as Cap | Weaker / overloaded |

## Rejected design patterns

| Pattern | Reason |
|---------|--------|
| Session alone as authority | Violates Cap-only truth |
| Free I/O at kernel boundary | Violates Ops-only effects |
| Correlation id as permission | Violates trace ≠ authority |
| Best-effort Cap verify | Violates fail closed |
| Widening attenuation | Violates monotonic limit |
| Peer minting root Caps | Violates Peer unprivileged |
| Second official vocabulary in docs | Violates one concept, one name |

## Process

When a proposal uses a rejected name or pattern:

1. Map it to an accepted concept if possible.  
2. If it cannot map, it is new power — run META gates (intention, axiom, layer, speech test).  
3. Do not “temporarily” use rejected names in the kernel.
