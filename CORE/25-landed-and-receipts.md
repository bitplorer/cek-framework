# CORE 25 — Authorized set, landed set, and receipts

Makes the apply-truth rule fully explicit. Optional for Baseline; normative when receipts are used.

---

## Definitions

| Term | Meaning |
|------|---------|
| **Authorized set** | Ops the Host placed in the Result after Cap verify (what was allowed to be carried out) |
| **Landed set** | Ops the Peer actually applied successfully |
| **Apply receipt** | Peer’s report of the landed set (and optional failures) |

Receipts are **not** Caps. They grant no authority (A1, A6, A7).

---

## Rules

1. **Lineage** records the **authorized** cause under Cap/Activity (and reverse plan).  
2. If **no receipt** → **reverse** uses the authorized set.  
3. If **receipt** present → **reverse** prefers the **landed** set.  
4. Partial apply does not invent Host truth; Peer does not widen Ops.  
5. Baseline interop does **not** require receipts.  
6. High-assurance / multi-Peer profiles **should** use receipts (recommended; see PROPOSALS P4).

---

## Failure reporting

| Case | Handling |
|------|----------|
| All Ops landed | Receipt matches authorized set |
| Partial land | Receipt lists landed + failed; reverse uses landed |
| Receipt lost | Treat as no receipt → reverse authorized set; may over-compensate — policy may mark uncertainty |
| False receipt | Out of kernel scope (Peer compromise); Host still bound by Cap accounting |

---

## Relation to other concepts

```text
Cap → Intent → Host Result(Ops authorized)
                    ↓
              Peer apply → landed
                    ↓
         optional receipt → lineage annotation
                    ↓
         reverse(prefer landed if known)
```

---

## See also

- [09-lineage-reverse.md](09-lineage-reverse.md)  
- [20-errors-and-concurrency.md](20-errors-and-concurrency.md)  
- [19-conformance.md](19-conformance.md)  
- [../PROPOSALS/radical-minimal-downside.md](../PROPOSALS/radical-minimal-downside.md) (P4)  
