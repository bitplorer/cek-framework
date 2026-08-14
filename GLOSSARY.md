# Glossary

Short definitions of frozen concepts.  
**Pictures + “is / is not”:** [`CONCEPTS.md`](CONCEPTS.md)  
Full law: [`CORE/`](CORE/) · Navigation: [`INDEX.md`](INDEX.md)

| Term | Definition |
|------|------------|
| **Activity** | Bounded work with a lifetime that can end and reverse its lineage |
| **apply** | Carry out Ops |
| **Baseline** | Permanent shared contract for interop |
| **Cap** | Permission to submit a specific Intent |
| **Context** | Mediated visibility for an Activity (not ambient authority) |
| **Host** | Role that verifies Cap and decides truth |
| **inject** | Declare what an Activity requires |
| **Intent** | Sealed ask to change something |
| **isolate** | Separate a Context slice |
| **limit** | Restrict what may be seen or done |
| **lineage** | Cause trail under Cap/Activity for undo |
| **mint** | Create a Cap |
| **Ops** | Ordered changes that may be carried out |
| **part** | Composition unit loaded under a Cap |
| **Peer** | Role that only applies Ops |
| **profile** | Declared Peer apply abilities |
| **Result** | Answer to an Intent |
| **reverse** | Undo lineage / end Activity cleanly |
| **submit** | Send an Intent under a Cap |
| **trace** | Correlation of related Intents (not authority) |
| **authorized set** | Ops Host put in Result after Cap verify |
| **landed set** | Ops Peer actually applied successfully |
| **apply receipt** | Peer report of landed set (not a Cap) |
| **idempotency bind** | Optional claim so retried asks share one logical cause |
| **recovery Cap** | Narrow Cap used to submit compensation during reverse |

## Meta-framework terms

| Term | Definition |
|------|------------|
| **Axiom** | Non-negotiable constitutional rule |
| **Canonical speech** | Explanation using only frozen vocabulary |
| **Charter amendment** | Explicit change to locked META/CORE law |
| **Fusion** | Single law from explicit parents |
| **Intention partition** | Closed set of jobs every concept must map to |
