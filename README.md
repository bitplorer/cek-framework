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

**What this is:** frozen **law** (meanings and rules), not runnable code.

| Idea | Meaning |
|------|---------|
| **Cap** | Permission ticket |
| **Intent** | The ask under a Cap |
| **Host** | Decides — verify Cap, lineage, `Result{Ops}` |
| **Peer** | Only applies Ops |
| **Ops** | Ordered effects as **data** |
| **lineage / reverse** | Honest cancel and revoke |
| **Baseline** | Classic Ops that never silent-break |
| **trace** | Groups steps — **never** permission |

**Flow**

```text
mint → submit → verify → Ops → apply → end → reverse
```

| This repo | Other place |
|-----------|-------------|
| Meanings, axioms, kill criteria | **Here** |
| Build Host/Peer, contract, CI | [cek-runtime](https://github.com/bitplorer/cek-runtime) |

| This repo **is** | This repo **is not** |
|------------------|----------------------|
| Frozen vocabulary and axioms | An npm/cargo library |
| What “correct CEK” means | Runnable Host/Peer |
| Design review checklist | Wire codecs or UI widgets |

More detail: [CONCEPTS.md](CONCEPTS.md) · [CORE/QUICKSTART.md](CORE/QUICKSTART.md)

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
| [GLOSSARY.md](GLOSSARY.md) · [CHARTER.md](CHARTER.md) · [STABILITY.md](STABILITY.md) · [CHOICES.md](CHOICES.md) · [CONTRIBUTING.md](CONTRIBUTING.md) | Terms, freeze, how to change |

**Goals:** Cap-only · Ops-only · fail closed · lineage/reverse · Baseline · frozen names.  
**Non-goals:** Ship code, wire-as-law, UI catalogs — see [cek-runtime](https://github.com/bitplorer/cek-runtime).
