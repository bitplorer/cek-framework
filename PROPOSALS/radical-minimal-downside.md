# Radical improvements — massive upside, minimal downside

**Status:** Optional design proposals (not charter-frozen)

**Recommended for production profiles (still optional for Baseline):** **P1 Idempotency bind**, **P4 Apply receipt**.

Baseline remains valid without them; high-assurance / multi-Peer deployments should enable them.  
**Constraint:** Must not relax A1–A10, rename frozen vocabulary, or break Baseline.  
**Preference:** Profile / L6 / domain-registry features that Baseline Peers can ignore.

---

## Selection rule

A proposal qualifies only if:

1. **Upside is structural** (retries, audit, reverse, multi-peer trust, least privilege) — not a niche convenience.  
2. **Downside is bounded** — optional, ignorable, or additive; no new ambient authority.  
3. **Fits canonical speech** without new kernel nouns (or with at most one carefully justified term).

---

## P1 — Idempotency bind (safe retries) — RECOMMENDED

### Idea
Allow a Cap (or Intent under Cap) to carry an optional **idempotency bind**: the Host treats duplicate submits of the same bind as one logical cause.

### Upside
- Network retries stop double-charging, double-morph, double lineage.  
- Agents and UIs can safely resubmit.  
- Massive operational reliability.

### Downside
- Minimal: optional claim; Baseline Peers ignore it.  
- Host must store idempotency keys (same class of store as single-use).  
- Fail closed if store required and down (consistent with A5).

### Axiom fit
Strengthens A3/A5; does not weaken Cap-only truth.

### Speech
“Submit Intent under Cap; Host deduplicates by idempotency bind before lineage.”

### Recommendation
**Adopt as optional Cap claim + Host policy** (L6/L1 behavior). Highest priority.

---

## P2 — Op effect class in domain registries

### Idea
Every domain Op declares a class:

- **observe** — no shared-world mutation  
- **mutate** — changes shared world (lineage-relevant)  
- **reverse_hint** — preferred inverse template reference  

### Upside
- Profiles can allow observe-only Peers (read surfaces, auditors).  
- Lineage can skip pure observe Ops.  
- Reverse becomes catalog-driven instead of ad hoc.

### Downside
- Catalog discipline cost only.  
- Baseline can treat unknown class as mutate (safe default).

### Axiom fit
Supports A2/A3; least privilege without new authority path.

### Recommendation
**Adopt in L5 registry schema**; Baseline default = mutate.

---

## P3 — Strict inverse/compensation declaration (profile)

### Idea
A **strict-reverse** profile requires every mutate Op to declare either:

- an inverse Op, or  
- a compensation Intent template, or  
- explicit `non_reversible` with audit reason class.

### Upside
- Unload/revoke stops being aspirational.  
- Domain authors confront irreversibility early.  
- Huge quality bar for serious deployments.

### Downside
- Not required for Baseline (no interop break).  
- More work for domain authors who opt into the profile.

### Recommendation
**Optional profile flag**; Hosts may require it for high-assurance Activities.

---

## P4 — Apply receipt (optional Peer → Host) — RECOMMENDED

### Idea
After apply, Peer may return a **receipt**: which Ops were applied, which failed, integrity reference.

Host attaches receipt to lineage.

### Upside
- Multi-peer and intermittently connected apply become auditable.  
- Reverse knows what actually landed.  
- Detects partial apply without trusting silence.

### Downside
- Optional; Baseline works without receipts.  
- Must not become a second authority (receipt ≠ Cap).

### Speech
“Peer applies Ops and may acknowledge with a receipt into lineage.”

### Recommendation
**Optional L4/L6**; high value for agents and multi-device.

---

## P5 — Machine-readable Baseline manifest

### Idea
Hosts and Peers exchange a small **manifest**: Baseline generation, supported profiles, required failure modes (fail closed behaviors).

### Upside
- Automated conformance and negotiation.  
- Prevents “almost compatible” silent drift.  
- Language-grade tooling surface.

### Downside
- One more document to version; keep it tiny.  
- Must not encode policy that bypasses Cap.

### Recommendation
**Adopt**; pairs with CORE/19 conformance.

---

## P6 — Time-boxed Activities (default policy, not axiom)

### Idea
Activities carry an optional deadline; on expiry Host reverse lineage (same as end).

### Upside
- Fewer abandoned checkouts/agent runs holding power or partial state.  
- Natural least privilege in time.

### Downside
- Policy default only; can be disabled per Activity.  
- Clock skew is operational, not a law change.

### Recommendation
**L7/L6 default** for product Activities; not a new kernel noun.

---

## P7 — Hash-chained lineage (optional L6)

### Idea
Lineage entries form a hash chain (or append-only log) per Activity or Cap.

### Upside
- Tamper-evident accountability.  
- Multi-Host forensics.  
- Enables later distributed agreement without changing Intent/Cap law.

### Downside
- Storage and compute cost; optional.  
- Does not replace Cap verify.

### Recommendation
**Optional high-assurance mode**.

---

## P8 — Separation of grantor policy from Cap token

### Idea
Document as hard practice: *who may mint* is policy (meta-Cap / bootstrap); *what the Cap allows* is the Cap. Never collapse “admin session” into Cap binds.

### Upside
- Prevents the most common real-world capability system failure.  
- Almost pure documentation/process; near-zero downside.

### Recommendation
**Elevate in CORE/14 and bootstrap training**; already implied — make unavoidable.

---

## Explicitly rejected “radical” ideas (downside too high)

| Idea | Why rejected |
|------|----------------|
| Trace as soft session auth | Breaks A6; massive downside |
| Peer self-mint root Caps for offline | Breaks A7 |
| Automatic ambient refresh Caps without mint policy | Ambient authority creep |
| Full IFC in Baseline | Huge complexity; keep L6 optional |
| Renaming Cap→Permit for marketing | Breaks vocabulary freeze for weak gain |
| Global distributed consensus in L1 | Topology lock-in; push to L6 |

---

## Priority order (expected ROI)

1. **P1 Idempotency bind** — operational correctness  
2. **P2 Op effect class** — least privilege + cleaner lineage  
3. **P3 Strict reverse profile** — real unload/revoke  
4. **P5 Baseline manifest** — tooling and stability  
5. **P4 Apply receipt** — multi-peer honesty  
6. **P6 Time-boxed Activities** — default hygiene  
7. **P7 Hash-chained lineage** — high-assurance audit  
8. **P8 Grantor/Cap separation emphasis** — prevent classic failure mode  

---

## Adoption rule under charter

These are **not** automatic CORE freezes.  
To adopt:

1. Canonical speech pass  
2. Place in L4–L6 (or registry)  
3. Baseline ignore/lower path  
4. Conformance vectors  
5. Only then optional charter note in CHARTER amendment log  

No proposal here requires relaxing A1–A10.
