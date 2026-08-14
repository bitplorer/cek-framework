# META 08 — Permanence and change

## Rule

Define a **Baseline** that correct old and new participants always share.  
Prefer additive power above Baseline.  
Meaning changes require versioning, dual-speak, and conformance.  
**Conformance defines correctness**, not narrative alone.

## Why

Meta-languages die when every improvement is a flag day.  
They also die when “compatibility” means forever carrying unsafe escapes.

Permanence is about the **law shape** (Intent under Cap → Result of Ops), not freezing every domain Op forever.

## Baseline (concept)

The Baseline is the permanent shared contract:

- Sealed ask under Cap  
- Result carrying ordered Ops  
- Host verify / Peer apply split  
- Classic apply ability sufficient for interop  

Richer profiles may exist; they must lower or no-op to Baseline when the peer cannot apply more.

## Change classes

| Class | Handling |
|-------|----------|
| Additive domain Ops | Allowed; Baseline peers ignore or receive projected classic Ops |
| Optional meta | Peers may ignore |
| Kernel meaning change | Major version; dual-speak window; new conformance vectors |
| Axiom relaxation | Charter amendment + version impact |
| Primary rename of kernel concept | Forbidden (alias only) |

## Downgrades

Removing power is allowed only if Baseline clients remain correct.  
Prefer profile negotiation (“peer cannot apply X”) over breaking Baseline.

## Conformance

Golden vectors should cover at least:

- Cap verify success and failure modes  
- once/single-use fail closed when store unavailable  
- Baseline projection  
- Unknown meta ignored  
- Unknown Ops policy  
- Lineage recorded and reversed on Activity end (where required)  
- Trace does not substitute for Cap  

(Exact encodings are implementation; the *behaviors* are charter-level.)
