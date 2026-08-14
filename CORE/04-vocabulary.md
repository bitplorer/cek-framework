# CORE 04 — Vocabulary (frozen)

## Nouns

| Name | Meaning |
|------|---------|
| **Intent** | Sealed ask to change something |
| **Cap** | Permission to submit that Intent |
| **Ops** | Ordered changes that may be carried out |
| **Result** | Answer to an Intent |
| **Activity** | Bounded work that starts, ends, and can be reversed |
| **Context** | What an Activity is allowed to see (not ambient authority) |
| **lineage** | Cause trail under Cap/Activity for undo |
| **Host** | Side that verifies Cap and decides truth |
| **Peer** | Side that only applies Ops |
| **Baseline** | Permanent shared contract |
| **profile** | Declared Peer apply abilities |
| **part** | Composition unit loaded under a Cap |
| **trace** | Correlation of related Intents (not power) |

## Verbs

| Name | Meaning |
|------|---------|
| **mint** | Create a Cap |
| **submit** | Send an Intent under a Cap |
| **apply** | Carry out Ops |
| **inject** | Declare what an Activity requires |
| **limit** | Restrict what may be seen or done |
| **isolate** | Separate a Context slice |
| **reverse** | Undo lineage / end Activity cleanly |

## Concept vs encoding

The framework names **concepts**.  
Implementations may use identifiers and token encodings; those are not additional kernel concepts.

## Rejected primary names

Fiber, Floor, run (execute or correlation concept), flow, thread, group/related as correlation concept, history/record as cause-trail concept, plugin as ambient load, command as Intent, token as Cap.
