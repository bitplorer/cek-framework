# CORE 13 — Canonical story

The entire core must remain tellable as follows:

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

## Full lifecycle narrative

1. **Bootstrap** — Host holds minimal root policy to mint Caps (explicit, not ambient Peer power).  
2. **Open Activity** — Cap-gated; Context mediated; inject requirements; optional limit/isolate.  
3. **Load parts** — under Caps into the Activity.  
4. **Step** — mint/use Cap → submit Intent → verify → lineage entry → Result Ops → Peer apply.  
5. **Correlate** — multiple steps may share a trace without sharing authority.  
6. **End** — reverse Activity lineage; unload parts; release Context mediation.  
7. **Interop** — all of the above remains expressible on Baseline; profiles only enrich apply ability.

If a proposed feature cannot be inserted into this narrative without new kernel nouns, it fails the speech test.
