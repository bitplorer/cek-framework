# CORE 03 — Axioms

These are constitutional. Features may not relax them without charter amendment.

| ID | Name | Statement |
|----|------|-----------|
| A1 | Cap-only truth | The only proof of authority is a verified Cap. Sessions, mesh membership, and ambient Context never suffice alone. |
| A2 | Ops-only effects | The only side-effects at the kernel boundary are explicit ordered Ops. |
| A3 | Lineage accountability | Every carried-out change under a revocable Cap or endable Activity is recorded in lineage. |
| A4 | Baseline permanent | The Baseline contract never silently breaks; power is additive or explicitly versioned. |
| A5 | Fail closed | Failed Cap verification, missing required once-store, or required lineage write failure refuses the action. |
| A6 | Trace ≠ authority | A trace only groups Intents; it never grants permission. |
| A7 | Peer unprivileged | A Peer applies Ops; it does not mint root Caps or invent business truth. |
| A8 | Attenuation monotonic | limit and isolate only narrow authority or visibility; they never widen it. |
| A9 | Composition authorized | Opening an Activity or loading a part is Cap-gated (or uses an explicit minimal bootstrap root). |
| A10 | One concept, one name | The kernel has no synonyms; documentation and code use the same primary names. |

## Notes

- **Bootstrap root** is allowed only as an explicit, minimal Host-side origin of Caps — not as ambient peer power. See `CORE/15-bootstrap.md`.  
- **Non-revocable, non-endable** paths may narrow lineage requirements only under explicit policy that does not create a general ambient escape.  
- **Projection determinism:** for fixed Intent outcome, profile, and projection rules, Host Ops projection should be deterministic (`CORE/17-extensibility.md`).  
- **Key purpose separation:** Cap authority material is conceptually distinct from transport and optional proof/telemetry material (`CORE/14-security-model.md`).
