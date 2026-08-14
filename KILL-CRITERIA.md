# Kill criteria — when it is not CEK

An implementation, fork, or “CEK-inspired” system **may not claim CEK alignment** if any of the following hold.

---

## Instant disqualification

| ID | Criterion |
|----|-----------|
| K1 | Shared-world change is allowed **without** a verified Cap (except documented Host-only bootstrap mint) |
| K2 | Kernel boundary emits free side-effects outside ordered **Ops** (and lineage accounting) |
| K3 | **Peer** can mint **root** Caps or is treated as source of business truth |
| K4 | **trace** (or correlation id) is accepted as permission or session authority |
| K5 | Cap verification is best-effort: failures still apply mutate effects |
| K6 | Single-use / once constraints are skipped when the required store is down (must **refuse**) |
| K7 | **limit** / attenuation can **widen** rights beyond the parent Cap/Context |
| K8 | Activity / part composition loads as ambient **plugin** power without Cap (or bootstrap) |
| K9 | Baseline interop is silently broken for correct old Host/Peer pairs |
| K10 | Primary kernel vocabulary is renamed or synonym-forked as a second official language |

---

## Soft fail (not CEK-compatible claim until fixed)

| ID | Criterion |
|----|-----------|
| K11 | Revocable Cap or endable Activity mutates shared world with **no** lineage |
| K12 | Activity end or Cap revoke reports success while reverse failed, without **non-reversible** mark |
| K13 | Compatibility claim without Baseline-lowering path for unknown rich Ops |
| K14 | Compatibility claim without tests for Cap reject and reverse-on-end (see CORE/19) |

---

## Still allowed (not kill)

- Incomplete domain Op catalogs  
- Missing optional PROPOSALS (idempotency, receipts) on Baseline-only deployments  
- Multiple Host/Peer processes  
- L7 bugs under a *valid* Cap (constrained, but possible)  
- Stronger L6 policy than Baseline  

---

## Use

- Gate marketing and conformance badges.  
- Linked from [CHARTER.md](CHARTER.md) and [CORE/QUICKSTART.md](CORE/QUICKSTART.md).  
- Changing these criteria is a charter amendment.
