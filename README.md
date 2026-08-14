# CEK — Cap-Effect Meta-Language

**The rulebook for who may change a shared world, how the change is listed, and how it is undone.**

This repository is **law and vocabulary only** — not a package you install.  
To implement Host and Peer kernels, use **[cek-runtime](https://github.com/bitplorer/cek-runtime)**.

| Start here | Link |
|------------|------|
| 10-minute core | [CORE/QUICKSTART.md](CORE/QUICKSTART.md) |
| **All concepts (glance)** | [CONCEPTS.md](CONCEPTS.md) |
| Still CEK? | [KILL-CRITERIA.md](KILL-CRITERIA.md) |
| Full index | [INDEX.md](INDEX.md) |
| Build kernels | [cek-runtime](https://github.com/bitplorer/cek-runtime) |

---

## Problems this solves

| Pain | Failure mode | CEK rule |
|------|--------------|---------|
| Agent or UI “just writes” DOM / DB / device | No clear permission; weak audit | Shared change requires a **Cap** |
| Effects hidden in callbacks | Hard to replay, test, or bound | Boundary effects only as ordered **Ops** (data) |
| Session / trusted peer / admin flag = power | Ambient authority | **Host** verifies; **Peer** only applies |
| Cancel job / unload / revoke | Partial cleanup; fake success | **lineage** + **reverse** (or non-reversible mark) |
| New release breaks old clients | Flag-day interop | **Baseline** Ops remain valid |
| Multi-step flow treated as login | Correlation as permission | **trace** groups steps; each step still needs a Cap |

**Fits:** tool-using agents, collab/multiplayer surfaces, DOM/UI channels, device or robot commands, any path where “who authorized this write?” must stay answerable.

**Skip this repo** if you only need a local app with no cross-boundary authority story — or open [cek-runtime](https://github.com/bitplorer/cek-runtime) when you want implementation design, not law.

---

## What CEK is

A **meta-language**: fixed names and rules for ask → allow → carry out → bound work → remember/undo. Not a day-to-day programming syntax.

```text
Host mints a Cap (permission ticket).
Caller submits an Intent under that Cap.
Host verifies the Cap — refuse means zero side effects.
Host returns a Result with Ops (the effect list).
Peer applies Ops (e.g. dom.morph, kv.set) — it does not grant itself power.
When the Activity ends (or Cap is revoked), Host reverses lineage.
Peer may apply inverse/restore Ops; completing a morph does not auto-undo.
```

Every term above is expanded with boxes and “is / is not” in **[CONCEPTS.md](CONCEPTS.md)**.

| Term | Meaning |
|------|---------|
| **Cap** | Ticket for one class of ask |
| **Intent** | The ask |
| **Host** | Authority — decide |
| **Ops** | Ordered effects as data |
| **Peer** | Apply surface (UI, agent, device) |
| **Activity** | Bounded job with a lifetime |
| **lineage** | Cause trail for undo/revoke |
| **Baseline** | Classic Ops that stay understandable |

---

## How to use this repo

1. Read [CORE/QUICKSTART.md](CORE/QUICKSTART.md) or skim [CONCEPTS.md](CONCEPTS.md).  
2. Check designs against [KILL-CRITERIA.md](KILL-CRITERIA.md).  
3. Keep one vocabulary — no second official names for Cap, Ops, Host, Peer.  
4. Implement via [cek-runtime](https://github.com/bitplorer/cek-runtime) (or a port that honors the same conformance idea).

---

## Name

Official name: **CEK** (Cap-Effect Meta-Language).  
**Ops** is the effect list, not the language name.

## Goals

| Secure | Flexible | Stable |
|--------|----------|--------|
| Cap-only, Ops-only, fail closed, lineage/reverse | profile, domain Ops, Activity above the law | Frozen vocabulary, Baseline, conformance |

## Map

| Path | Role |
|------|------|
| [CONCEPTS.md](CONCEPTS.md) | All concepts at a glance |
| [META/](META/) | How the core is derived and amended |
| [CORE/](CORE/) | Language law (00–27) |
| [diagrams/](diagrams/) | Conceptual flows (Mermaid optional) |
| [PROPOSALS/](PROPOSALS/) | Optional extensions (not frozen) |
| [GLOSSARY.md](GLOSSARY.md) · [CHARTER.md](CHARTER.md) · [STABILITY.md](STABILITY.md) · [CHOICES.md](CHOICES.md) | Terms, freeze, guarantees, rationale |

## Reading order

1. [QUICKSTART](CORE/QUICKSTART.md) or [CONCEPTS](CONCEPTS.md) + [KILL-CRITERIA](KILL-CRITERIA.md)  
2. [CORE/SUMMARY.md](CORE/SUMMARY.md)  
3. Detail as needed · [CHARTER.md](CHARTER.md)

## Non-goals

Runnable code, wire encodings as law, product UI catalogs, marketing renames.  
Implementation: [cek-runtime](https://github.com/bitplorer/cek-runtime).
