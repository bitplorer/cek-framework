# CORE 21 — Intent, Result, and Ops (conceptual shape)

Conceptual fields only. Encodings are free as long as binds hold.

## Intent

An **Intent** is a sealed ask. Conceptually it carries:

| Element | Role |
|---------|------|
| **action** | What is being asked |
| **args** | Arguments; sealed subset bound by Cap |
| **Cap** | Permission for this ask (when required by policy) |
| optional **trace** association | Correlation only |
| optional other meta | Ignorable on Baseline if unknown |

Without a valid Cap when policy requires one, Host refuses (A1, A5).

## Result

A **Result** answers an Intent. Conceptually it carries:

| Element | Role |
|---------|------|
| **ok** / success signal | Whether the ask was accepted and handled |
| **Ops** | Ordered changes to carry out (may be empty) |
| **error** | On failure; authority refusal distinct from business miss when possible ([20](20-errors-and-concurrency.md)) |
| optional meta | Never authority |

## Ops

**Ops** are an ordered list of carry-out instructions.

Rules:

1. Order is significant within one Result.  
2. Ops are **data**, not code (no Baseline eval).  
3. Unknown Ops: ignore, soft-fail, or strict-reject per **profile** — never crash the kernel.  
4. Domain meaning lives in L5 namespaces; law does not fix the catalog.

## Projection

Host may **project** rich internal outcomes to Ops the Peer’s profile can apply, always able to fall back to **Baseline** forms ([11](11-baseline-profile.md), [17](17-extensibility.md)).
