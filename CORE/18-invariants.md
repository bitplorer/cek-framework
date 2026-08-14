# CORE 18 — Invariants checklist

Use this list in design review and conformance.  
Any “no” on a required invariant blocks merge of a kernel change.

## Authority

- [ ] Shared-world change requires verified Cap (or documented Host bootstrap mint only)  
- [ ] Session/cookie/mesh membership never alone authorizes  
- [ ] Single-use constraints consumed before side-effects  
- [ ] Missing required once-store refuses  
- [ ] Attenuation only narrows  

## Effects

- [ ] Kernel boundary emits only ordered Ops (plus lineage accounting)  
- [ ] No eval/raw code Op as Baseline power  
- [ ] Peer apply is the mutation path for delivered Ops  

## Composition

- [ ] Activity open / part load is Cap-gated (or bootstrap)  
- [ ] inject declares requirements; undeclared access fails under mediation  
- [ ] isolate/limit do not grant parent’s missing rights  

## Accountability

- [ ] Revocable Cap or endable Activity → lineage recorded  
- [ ] Activity end triggers reverse  
- [ ] Failed reverse is not reported as clean success without non-reversible mark  

## Correlation

- [ ] trace does not authorize  
- [ ] Each step still has its own Cap  
- [ ] Resume does not revive dead Caps via trace alone  

## Interop

- [ ] Baseline path still works  
- [ ] Unknown optional meta ignorable  
- [ ] Profile cannot mint authority  

## Language hygiene

- [ ] No new primary kernel synonym  
- [ ] Canonical speech still holds  
- [ ] Layer placement correct; no upward dependency of L0–L2 on L5–L7  
