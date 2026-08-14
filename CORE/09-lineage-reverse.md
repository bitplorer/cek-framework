# CORE 09 — Lineage and reverse

## lineage

**lineage** is the cause trail of what was carried out under a **Cap** and/or **Activity**.

It exists so authority end and Activity end have a defined undo story (axioms A3, accountability loop).

### Conceptual entry contents

A lineage entry conceptually ties:

- Cap identity (or equivalent),  
- Activity identity (when applicable),  
- optional **trace** association (correlation only),  
- action,  
- sealed argument integrity reference,  
- Ops carried out (or their integrity reference),  
- a **reverse plan** (inverse and/or compensation).

### lineage is not

- generic application history,  
- full observability telemetry,  
- a substitute for Cap,  
- a substitute for trace.

## reverse

**reverse** undoes a lineage (or ends an Activity by undoing its lineage).

### Forms

1. **Inverse** — direct undo of caused Ops where possible.  
2. **Compensation** — new Intents under a recovery Cap when true inverse is impossible.  
3. **Mark non-reversible** — explicit audit outcome when neither inverse nor compensation can complete; never silent success.

## When lineage is required

Required when:

- the Cap is revocable, or  
- the Activity is endable and may have caused shared-world change.

Optional narrowing only under explicit non-revocable / non-endable policy that does not become a general escape hatch.

## Order

Reverse plans should respect causal order (typically reverse order of causes) unless a documented compensation graph says otherwise.

## Host cause vs landed set (normative)

- **Lineage** always records what the **Host authorized** (cause under Cap/Activity).
- A Peer may optionally return an **apply receipt** (which Ops actually landed).
- Receipts are **not** Caps and grant no authority.
- When receipts exist, **reverse** prefers the **landed set**; when absent, reverse uses the authorized Ops set.
- Baseline interop does **not** require receipts.

## See also

- [19-conformance.md](19-conformance.md)
- [20-errors-and-concurrency.md](20-errors-and-concurrency.md)
- [24-moving-parts-and-corners.md](24-moving-parts-and-corners.md)
- [25-landed-and-receipts.md](25-landed-and-receipts.md)
- [27-recovery-cap.md](27-recovery-cap.md)
