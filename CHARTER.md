# Charter — Freeze and Amendment

## Freeze statement

The following are **locked** as of this repository:

1. The **meta-framework** under `META/`  
2. The **core framework** under `CORE/` (including hardening docs 14–27)  
3. **Vocabulary** — `CORE/04-vocabulary.md`  
4. **Axioms** — `CORE/03-axioms.md`  
5. **Layer model** — `CORE/05-layers.md`  
6. **Stability guarantees** — `STABILITY.md`  

`PROPOSALS/` is **not** frozen until explicitly adopted.

## What may change without charter amendment

- Domain drivers and op namespaces (L5)  
- Application handlers and product logic (L7)  
- Optional policy (L6) that does **not** relax axioms  
- Additive optional meta that Peers may ignore  
- Conformance vector *additions* that clarify existing law  
- Draft text under `PROPOSALS/`  

## What requires charter amendment

- Any change to axioms  
- Any rename of a frozen kernel concept (primary name)  
- Any new ambient authority path  
- Treating **trace** as authority or as execute  
- Breaking Baseline interop for correct old Host/Peer pairs  
- Introducing a third conceptual parent that redefines L0–L2  
- Collapsing Host and Peer into one privileged role  
- Widening bootstrap beyond Host-only minimal mint  

## Amendment process (required)

1. State the proposal in **canonical speech** (`META/10`).  
2. Classify layer and change type (`CORE/12`).  
3. Show axiom impact (none, or explicit axiom edit).  
4. Show naming impact (no synonym drift).  
5. Show Baseline impact (still holds, or major version plan).  
6. Run **invariants** (`CORE/18`) and update **conformance** (`CORE/19`).  
7. Record the amendment in the log below with date and rationale.

## Dual vocabulary ban

Documentation and design discussion use the **same** kernel words as the core vocabulary.  
Tutorial glosses are allowed once; they do not create second official names.

## Stability binding

Implementations that claim CEK alignment must honor:

- [STABILITY.md](STABILITY.md)  
- [CORE/16-versioning.md](CORE/16-versioning.md)  
- [CORE/18-invariants.md](CORE/18-invariants.md) on kernel changes  
- [CORE/19-conformance.md](CORE/19-conformance.md)  

## Kill criteria binding

Claims of CEK alignment must not violate [KILL-CRITERIA.md](KILL-CRITERIA.md).

## Security binding

Kernel designs must remain consistent with:

- [CORE/14-security-model.md](CORE/14-security-model.md)  
- [CORE/15-bootstrap.md](CORE/15-bootstrap.md)  

## Amendment log

| Date | Change | Rationale |
|------|--------|-----------|
| 2026-08-14 | Initial META + CORE 00–13 lock | First freeze of CEK conceptual law |
| 2026-08-14 | CORE 14–20, STABILITY, GLOSSARY | Security, bootstrap, versioning, extensibility, invariants, conformance, errors |
| 2026-08-14 | PROPOSALS/ (unfrozen) | Optional high-ROI extensions; not law until adopted |
| 2026-08-14 | INDEX + polish | Navigation and consistency |
| 2026-08-14 | CORE 21–23, COMPLETENESS | Intent/Result/Ops shape, sealed args, scenarios, audit |
| 2026-08-14 | CORE 24 | Moving parts and missing corners doctrine |
| 2026-08-14 | STYLE.md | Documentation clarity and consistency rules |
| 2026-08-14 | QUICKSTART, KILL-CRITERIA, conf/lineage/manifest upgrades | Council improvements |
| 2026-08-14 | Denoise hubs (README/SUMMARY/COMPLETENESS) | Clarity without capability loss |
| 2026-08-14 | CONTRIBUTING, corner diagram, polish 09/STABILITY | Post-denoise enhancements |
| 2026-08-14 | CORE 25–27 | Explicit landed/receipts, idempotency, recovery Cap |
| 2026-08-14 | CORE 00/06/08 + CHOICES/COMPLETENESS | Framework name clarity; closed L1 set; ordered Host pipeline; Cap lifecycle; cross-Host Caps; implementation boundary |
