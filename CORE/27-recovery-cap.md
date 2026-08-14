# CORE 27 — Recovery Cap (explicit)

Used when **reverse** must submit compensation Intents.

---

## Meaning

A **recovery Cap** is a Cap minted under Host policy whose actions are limited to **compensation / cleanup** for a given lineage (or Activity).

It is still a normal Cap: verify, sealed args, fail closed, lineage for its own effects if revocable.

---

## Rules

1. Recovery Caps are **minted by Host** (or meta-Cap), never by Peer as root power.  
2. Scope is **narrow**: only the compensation actions declared for that reverse plan.  
3. Compensation Intents are ordinary Intents under the recovery Cap.  
4. If compensation itself fails → **mark non-reversible** for the original cause; do not report clean reverse.  
5. Bootstrap must not be used as a standing recovery bypass.

---

## Flow

```text
Activity end / Cap revoke
  → reverse(lineage)
      → inverse Ops when possible
      → else submit compensation Intents under recovery Cap
      → else mark non-reversible + audit
```

---

## See also

- [09-lineage-reverse.md](09-lineage-reverse.md)  
- [15-bootstrap.md](15-bootstrap.md)  
- [08-cap.md](08-cap.md)  
