# CORE 14 — Security model (hardening)

## Goal

State what the core **guarantees**, what it **does not guarantee**, and which threats are in scope at L0–L2.

## Trust boundaries

| Boundary | Trusted for | Not trusted for |
|----------|-------------|-----------------|
| **Host** | Cap mint/verify policy, truth for dispatch, lineage record | Blind trust of Peer-supplied “I am allowed” |
| **Peer** | Faithful apply of Ops it accepts under profile | Minting root Caps; inventing business truth |
| **Caller holding a Cap** | Submitting the bound Intent | Widening sealed args; replaying single-use Caps |
| **trace** | Grouping Intents | Permission or execute |

## Threats in scope (kernel must address)

| Threat | Primary controls |
|--------|------------------|
| Forged or tampered ask | Cap integrity bind to action + sealed args |
| Replay of single-use permission | Single-use consume before side-effects; fail closed if store unavailable |
| Ambient privilege | A1 Cap-only; A7 Peer unprivileged; A9 composition authorized |
| Residual effects after revoke/end | A3 lineage + reverse |
| Confused deputy / arg mutation | Sealed args bind; handler reloads truth from store for magnitudes |
| Correlation used as auth | A6 |
| Silent widening of power | A8 monotonic attenuation |
| Peer overreach | Ops-only apply; no root mint |
| Compatibility break as attack on dependents | A4 Baseline permanent |

## Threats out of kernel scope (must be handled elsewhere)

| Threat | Where |
|--------|--------|
| Side channels (timing, power, traffic analysis) | L6/L7, deployment, crypto engineering |
| Full information-flow non-interference | Optional L6 IFC; not required of Baseline |
| Physical host compromise | Ops / platform security |
| Social engineering of Cap grantors | Organizational policy; meta-Cap governance |
| Poisoned domain drivers | L5 review; still cannot bypass Cap verify if Host is correct |
| Denial of service by volume | L6 budgets/quotas; platform limits |

## Security design rules

1. **Never** open a path that changes the shared world without a verified Cap (except documented bootstrap mint on Host).  
2. **Never** treat transport security alone as Cap.  
3. **Never** skip single-use consumption ordering (consume before effects).  
4. **Never** report successful reverse when compensation/inverse failed without explicit non-reversible mark.  
5. **Separate key purposes**: Cap authority material ≠ transport keys ≠ optional proof/telemetry keys (conceptual separation; implementations must honor it).

## Capability discipline summary

```text
Mint is rare and Host-side (or meta-Cap gated).
Hold is transferable only by attenuation or explicit grant policy.
Use is Intent submit under Cap.
End is revoke Cap and/or end Activity → reverse lineage.
```
