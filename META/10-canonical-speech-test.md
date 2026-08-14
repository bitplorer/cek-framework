# META 10 — Canonical speech test

## Rule

A design is aligned only if it can be stated in short sentences using the **frozen vocabulary** and **intention set** — without inventing new kernel words.

If a new kernel word is required to explain the design, either:

- the design is incomplete, or  
- the freeze must be amended first.

## Canonical sentences (CEK)

```text
Host mints a Cap.
Caller submits an Intent under that Cap.
Host verifies Cap, records lineage, returns Result with Ops.
Peer applies Ops.

Work is an Activity in a Context.
The Activity injects what it needs; the Host may limit or isolate it.
Parts load under Caps.

Related Intents share a trace.
When an Activity ends, reverse its lineage.

Everyone supports the Baseline.
Profile only negotiates what a Peer can apply.
```

## How to use the test

1. Write the proposal as a paragraph.  
2. Rewrite it using only canonical sentences plus domain Op names.  
3. List any extra nouns/verbs you needed.  
4. Extra kernel candidates → reject, relocate to L5–L7, or start charter amendment.  

## Examples

**Aligned:** “Checkout is an Activity; each payment Intent requires a Cap; abandon reverses lineage; steps share a trace.”

**Misaligned:** “The flow engine runs a sandbox session plugin that elevates tokens.”  
→ Uses rejected names and ambient patterns; rewrite or reject.
