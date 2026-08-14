# CEK — Cap-Effect Meta-Language

**The rulebook for “who may change a shared world, how the change is listed, and how it is undone.”**

This repo is **law and vocabulary only** — not an npm/cargo package.  
To *build* Host/Peer kernels, see **[cek-runtime](https://github.com/bitplorer/cek-runtime)**.

| | |
|--|--|
| **10-minute start** | [CORE/QUICKSTART.md](CORE/QUICKSTART.md) |
| **“Is this still CEK?”** | [KILL-CRITERIA.md](KILL-CRITERIA.md) |
| **Full index** | [INDEX.md](INDEX.md) |

---

## Real problems this is for

| Pain you may already have | What goes wrong | What CEK insists on |
|---------------------------|-----------------|---------------------|
| Agent or UI “just writes” the DOM / DB / device | No clear permission; hard to audit | Every shared change needs a **Cap** |
| Effects are hidden in callbacks and side channels | Can’t replay, test, or bound work | Effects leave the boundary only as ordered **Ops** (data) |
| Session / “trusted peer” / admin flag = power | Ambient authority, confused deputy | **Host** verifies; **Peer** only applies |
| Feature unload / revoke / “cancel the job” | Partial cleanup, silent “success” | **lineage** + **reverse** (or honest non-reversible mark) |
| New release breaks old clients | Flag-day interop | **Baseline** Ops always still work |
| Multi-step flows treated as a login | Correlation mistaken for permission | **trace** groups steps; each step still needs a Cap |

**Concrete examples:** tool-using agents that must not free-mutate production state; collaborative or multiplayer surfaces; DOM morph / UI channel pipelines; device or robot command paths; any service where “who authorized this write?” must be answerable after the fact.

**Not for:** a pure local app with no cross-boundary authority story — you don’t need this charter for that.

---

## What CEK is (in one breath)

A **meta-language**: fixed names and rules for ask → allow → carry out → bound work → remember/undo — not a syntax you program in day to day.

```text
Host mints a Cap (permission ticket).
You submit an Intent under that Cap.
Host checks the Cap — refuse means zero side effects.
Host returns a Result with Ops (the effect list).
Peer applies Ops (e.g. dom.morph, kv.set) — it does not grant itself power.
When the Activity ends (or Cap is revoked), Host reverses lineage.
Peer may apply inverse/restore Ops; it does not “auto-undo” just because a morph finished.
```

| Word | Everyday meaning |
|------|------------------|
| **Cap** | Ticket for one class of ask |
| **Intent** | The ask |
| **Host** | Authority service — decide |
| **Ops** | Ordered effects as data |
| **Peer** | Apply surface — UI, agent runtime, device |
| **Activity** | Bounded job with a lifetime |
| **lineage** | Cause trail for undo/revoke |
| **Baseline** | Forever-understandable classic Ops |

---

## What you do with *this* repo

1. Learn the rules ([QUICKSTART](CORE/QUICKSTART.md)).  
2. Design or review systems so they don’t violate [KILL-CRITERIA](KILL-CRITERIA.md).  
3. Speak one vocabulary (no second names for Cap/Ops/Host).  
4. Implement in **[cek-runtime](https://github.com/bitplorer/cek-runtime)** (or a port that passes the same conformance idea).

---

## Framework name

Official name: **CEK**. **Ops** is one kernel noun (the effect list), not the language name.

## Goals

| Secure | Flexible | Stable |
|--------|----------|--------|
| Cap-only, Ops-only, fail closed, lineage/reverse | profile, domain Ops, Activity — above the law | Frozen vocabulary, Baseline, conformance |

## Map

| Path | Role |
|------|------|
| [META/](META/) | How the core is derived and amended |
| [CORE/](CORE/) | Language law (00–27) |
| [diagrams/](diagrams/) | Flows (Mermaid; READMEs stay readable without it) |
| [PROPOSALS/](PROPOSALS/) | Optional extensions (**not frozen**) |
| [STABILITY.md](STABILITY.md) · [GLOSSARY.md](GLOSSARY.md) · [CHOICES.md](CHOICES.md) · [CHARTER.md](CHARTER.md) | Guarantees, terms, rationale, freeze |

## Reading order

1. [CORE/QUICKSTART.md](CORE/QUICKSTART.md) + [KILL-CRITERIA.md](KILL-CRITERIA.md)  
2. [CORE/SUMMARY.md](CORE/SUMMARY.md)  
3. Depth as needed · [CHARTER.md](CHARTER.md)

## Non-goals

Ship code, wire field paths as law, product UI catalogs, or marketing renames — implementation lives in [cek-runtime](https://github.com/bitplorer/cek-runtime).
