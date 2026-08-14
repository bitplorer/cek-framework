# CEK — Cap-Effect Meta-Language

**The rulebook for who may change a shared world, how the change is listed, and how it is undone.**

**Law and vocabulary only** — not a package.  
**Build kernels:** [cek-runtime](https://github.com/bitplorer/cek-runtime)

| Start here | Link |
|------------|------|
| Repo glance | ↓ below |
| All concepts | [CONCEPTS.md](CONCEPTS.md) |
| 10-minute core | [CORE/QUICKSTART.md](CORE/QUICKSTART.md) |
| Still CEK? | [KILL-CRITERIA.md](KILL-CRITERIA.md) |
| Index | [INDEX.md](INDEX.md) |

---

## This repo at a glance

```text
┌────────────────────────── cek-framework ──────────────────────────┐
│  LAW (not code)                                                   │
│                                                                   │
│  Cap  = permission ticket                                         │
│  Intent = the ask under a Cap                                     │
│  Host = decides (verify Cap, lineage, Result{Ops})                │
│  Peer = only applies Ops                                          │
│  Ops  = ordered effects as data                                   │
│  lineage + reverse = honest cancel / revoke                       │
│  Baseline = classic Ops that never silent-break                   │
│  trace = groups steps (never permission)                          │
│                                                                   │
│  Flow:  mint → submit → verify → Ops → apply → end → reverse      │
└───────────────────────────────────────────────────────────────────┘
         │ meanings & kill criteria              │ build Host/Peer
         ▼                                       ▼
   this repo                               cek-runtime
```

| This repo **is** | This repo **is not** |
|------------------|----------------------|
| Frozen vocabulary and axioms | An npm/cargo library |
| What “correct CEK” means | Runnable Host/Peer |
| Design review checklist | Wire codecs or UI widgets |

| Term | One line |
|------|----------|
| **Cap** | Ticket for one class of ask |
| **Intent** | The ask |
| **Host** | Authority — decide |
| **Peer** | Apply surface only |
| **Ops** | Effect list (data) |
| **Activity** | Bounded job; end → reverse |
| **lineage** | Cause trail for undo |
| **Baseline** | Permanent interop Ops |

Detail: [CONCEPTS.md](CONCEPTS.md) · [CORE/QUICKSTART.md](CORE/QUICKSTART.md)

---

## Problems this solves

| Pain | Failure mode | CEK rule |
|------|--------------|---------|
| Agent/UI “just writes” DOM, DB, or device | No clear permission | Shared change needs a **Cap** |
| Effects hidden in callbacks | Hard to replay or bound | Boundary effects only as **Ops** |
| Session / trusted peer / admin = power | Ambient authority | **Host** verifies; **Peer** applies |
| Cancel / unload / revoke | Fake or partial cleanup | **lineage** + **reverse** (or mark) |
| New release breaks old clients | Flag-day interop | **Baseline** stays valid |
| Multi-step flow treated as login | Correlation as permission | **trace** groups; Cap still required |

**Fits:** agents with tools, collab/UI channels, devices — anywhere “who authorized this write?” must stay answerable.  
**Skip:** pure local apps with no cross-boundary authority story.

---

## How to use this repo

1. Glance above → [CONCEPTS.md](CONCEPTS.md) or [QUICKSTART](CORE/QUICKSTART.md).  
2. Check designs against [KILL-CRITERIA.md](KILL-CRITERIA.md).  
3. One vocabulary only (no synonym names for Cap/Ops/Host).  
4. Implement in [cek-runtime](https://github.com/bitplorer/cek-runtime).

Official name: **CEK**. **Ops** is the effect list, not the language name.

---

## Map

| Path | Role |
|------|------|
| [CONCEPTS.md](CONCEPTS.md) | All concepts at a glance |
| [CORE/](CORE/) | Language law (00–27) |
| [META/](META/) | How the core is derived |
| [diagrams/](diagrams/) | Conceptual flows |
| [PROPOSALS/](PROPOSALS/) | Optional (not frozen) |
| [GLOSSARY.md](GLOSSARY.md) · [CHARTER.md](CHARTER.md) · [STABILITY.md](STABILITY.md) · [CHOICES.md](CHOICES.md) · [CONTRIBUTING.md](CONTRIBUTING.md) | Terms, freeze, style of change |

**Goals:** Cap-only · Ops-only · fail closed · lineage/reverse · Baseline · frozen names.  
**Non-goals:** Ship code, wire-as-law, UI catalogs — see [cek-runtime](https://github.com/bitplorer/cek-runtime).
