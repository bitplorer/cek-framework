# CORE 16 — Versioning (language stability)

## Goals

- Old correct Host/Peer pairs keep interoperating on **Baseline**.  
- New power is **opt-in** via profile or major meaning version.  
- Names of kernel concepts do not churn.

## Version kinds

| Kind | What changes | Compatibility |
|------|--------------|---------------|
| **Baseline behavior** | Never silently | Eternal for a given Baseline generation |
| **Profile revision** | Apply ability | Negotiated; fallback to Baseline |
| **Domain Op namespace** | L5 meanings | Unknown Ops ignored or projected |
| **Major law version** | Meaning of Intent/Cap/verify/apply | Dual-speak window required |
| **Charter amendment** | Axioms / meta-framework | Explicit; recorded in CHARTER.md |

## Stability guarantees (language-grade)

1. **Primary vocabulary freeze** — Intent, Cap, Ops, Result, Activity, Context, lineage, Host, Peer, Baseline, profile, part, trace, and core verbs do not rename.  
2. **Baseline interop freeze** — A Peer that only applies Baseline Ops continues to work with a Host that also speaks richer profiles.  
3. **Additive preference** — New fields/ops/profiles must be ignorable or lowerable when unknown.  
4. **No silent semantic shift** — Same name, same intention; if meaning changes, version the law.  
5. **Deprecation without deletion of Baseline** — Features above Baseline may deprecate; Baseline path remains.

## Dual-speak requirement

On major law version:

- Hosts that offer the new law must still accept Baseline-shaped participation for a documented window.  
- Conformance vectors exist for both shapes during the window.  
- End of window is a published date, not an accident.

## What is *not* frozen

- Domain Op catalogs  
- L7 product shapes  
- L6 optional policies  
- Encoding of Caps (as long as conceptual binds hold)  
- Transport  

## Implementation version vs law version

Library semver may move faster than law version.  
Law version changes only when CORE meaning changes.  
Document the mapping in releases; do not equate “npm major” with “Baseline break” unless it is one.
