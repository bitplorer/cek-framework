# CORE 00 — Overview

## Definition

The **Cap-Effect Meta-Language (CEK)** core is the locked law of authorized change across boundaries.

It is a **meta-language** in this sense: it defines how programs may *ask*, *be allowed*, *carry out*, *bound*, *remember*, and *undo* change — and how runtimes participate as **Host** or **Peer** under one contract. It is **not** a syntactic superset of Python, TypeScript, Rust, or any other language.

## Core in one line

**Mint Cap → submit Intent → apply Ops → bound in Activity → record lineage → reverse on end → group with trace → keep Baseline.**

## What the core fixes

| Problem | Core answer |
|---------|-------------|
| Ambient authority | Cap-only truth |
| Free side-effects | Ops-only effects |
| Ununloadable composition | Activity + lineage + reverse |
| Multi-step confused with permission | trace is correlation only |
| Flag-day interop | Baseline permanent |
| Decide/apply muddle | Host / Peer split |

## Document map

| Range | Topic |
|-------|--------|
| [01](01-parents.md)–[04](04-vocabulary.md) | Parents, intentions, axioms, vocabulary |
| [05](05-layers.md)–[13](13-canonical-story.md) | Layers, roles, Cap, lineage, trace, Baseline, change, story |
| [14](14-security-model.md)–[20](20-errors-and-concurrency.md) | Security, bootstrap, versioning, extensibility, invariants, conformance, errors |
| [SUMMARY](SUMMARY.md) | Denoised core |

## See also

- Meta-method: [`../META/SUMMARY.md`](../META/SUMMARY.md)
- Stability: [`../STABILITY.md`](../STABILITY.md)
- Glossary: [`../GLOSSARY.md`](../GLOSSARY.md)
- Index: [`../INDEX.md`](../INDEX.md)

## Explicit non-goals of the core

- Choosing specific Cap cryptography
- Mandating one process topology
- Defining all domain Ops
- Replacing general-purpose programming languages
