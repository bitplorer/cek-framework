# CEK — Cap-Effect Meta-Language

**The rulebook for who may change a shared world, how the change is listed, and how it is undone.**

**Core thesis.** CEK exists to make shared-world change Cap-only, Ops-only, and honestly reversible — so “who authorized this write, and how is it undone?” stays answerable.

**Law and vocabulary only** — not a package.  
**Build kernels:** [cek-runtime](https://github.com/bitplorer/cek-runtime) · [cek-python](https://github.com/bitplorer/cek-python) · [cek-hw](https://github.com/bitplorer/cek-hw) (L5 apply)

| Start here | Link |
|------------|------|
| Mental model | [docs/00-mental-model.md](docs/00-mental-model.md) |
| Ownership | [docs/01-architecture-and-ownership.md](docs/01-architecture-and-ownership.md) |
| Happy path | [docs/02-happy-path.md](docs/02-happy-path.md) |
| Current reality | [docs/03-current-reality.md](docs/03-current-reality.md) |
| All concepts | [CONCEPTS.md](CONCEPTS.md) |
| 10-minute core | [CORE/QUICKSTART.md](CORE/QUICKSTART.md) |
| Still CEK? | [KILL-CRITERIA.md](KILL-CRITERIA.md) |
| Index | [INDEX.md](INDEX.md) |

---

## Mental model

```text
mint Cap → submit Intent → Host verify
        → Result{Ops} → Peer apply
        → Activity bounds work → lineage records causes
        → end/revoke → reverse (or mark non-reversible)
        → trace only groups steps → Baseline always still works
```

```mermaid
flowchart LR
  mint[mint Cap] --> submit[submit Intent]
  submit --> verify[Host verify]
  verify -->|refuse| closed[fail closed]
  verify -->|ok| result[Result Ops]
  result --> apply[Peer apply]
  apply --> end[end / revoke]
  end --> reverse[reverse lineage]
```

Full diagram: [diagrams/00-mental-model.mmd](diagrams/00-mental-model.mmd). Reader page: [docs/00](docs/00-mental-model.md).

---

## Axioms

Constitutional text: [CORE/03-axioms.md](CORE/03-axioms.md). Compression:

1. **Cap-only truth** — Only a verified Cap is authority. (A1)
2. **Ops-only effects** — Kernel-boundary effects are ordered Ops. (A2)
3. **Host decides, Peer applies** — Exactly two L1 kernels. Peer does not mint root Caps. (A7)
4. **Lineage then reverse** — Revocable/endable paths record cause and undo, or mark non-reversible. (A3)
5. **Fail closed** — Bad Cap or required store down refuses. Zero mutate Ops. (A5)
6. **trace is not permission** — Correlation never grants, executes, or undoes. (A6)
7. **Baseline never silent-breaks** — New power is additive or versioned. Names do not fork. (A4, A10)

A8–A10 still bind: `limit`/`isolate` only narrow; composition is Cap-gated; one concept, one name.

---

## Ownership

| | Owns | Does *not* own |
|--|------|----------------|
| **This repo** | Meanings, axioms, frozen names, Host/Peer *role* law, kill criteria | Runnable kernels, wire codecs, crypto, Op catalogs, crates, CI |
| **Host** | Mint, verify, lineage, Result | Apply as mutation; Peer-said “I am allowed” |
| **Peer** | Apply Ops under profile | Root mint; business truth |
| **Cap** | Permission to submit a class of Intent | Session, TLS, trace, Activity lifetime |
| **trace** | Group related Intents | Permission |

Full table and layers: [docs/01](docs/01-architecture-and-ownership.md).

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
| Python Host + surface | [cek-python](https://github.com/bitplorer/cek-python) |
| L5 `hw.*` apply (not a Host) | [cek-hw](https://github.com/bitplorer/cek-hw) |

| This repo **is** | This repo **is not** |
|------------------|----------------------|
| Frozen vocabulary and axioms | An npm/cargo library |
| What “correct CEK” means | Runnable Host/Peer |
| Design review checklist | Wire codecs or UI widgets |

<details>
<summary>ASCII overview (wide screens)</summary>

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
└─────────────────────────────────────────────────────────────────┘
         │ meanings & kill criteria              │ build Host/Peer
         ▼                                       ▼
   this repo                               cek-runtime / cek-python
                                           cek-hw = L5 apply only
```

</details>

More detail: [CONCEPTS.md](CONCEPTS.md) · [CORE/QUICKSTART.md](CORE/QUICKSTART.md) · [docs/00](docs/00-mental-model.md)

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

1. [docs/00](docs/00-mental-model.md) → [CONCEPTS.md](CONCEPTS.md) or [QUICKSTART](CORE/QUICKSTART.md).
2. Walk [docs/02](docs/02-happy-path.md); check designs against [KILL-CRITERIA.md](KILL-CRITERIA.md).
3. One vocabulary only (no synonym names for Cap/Ops/Host).
4. Implement in [cek-runtime](https://github.com/bitplorer/cek-runtime) or [cek-python](https://github.com/bitplorer/cek-python). Domain apply packs (e.g. [cek-hw](https://github.com/bitplorer/cek-hw)) stay L5 — they are not Hosts.

Official name: **CEK**. **Ops** is the effect list, not the language name.

---

## Map

| Path | Role |
|------|------|
| [docs/](docs/) | Reader path — mental model, ownership, happy path, current reality |
| [CONCEPTS.md](CONCEPTS.md) | All concepts at a glance |
| [CORE/](CORE/) | Language law (00–27) |
| [META/](META/) | How the core is derived |
| [diagrams/](diagrams/) | Conceptual flows |
| [PROPOSALS/](PROPOSALS/) | Optional (not frozen) |
| [GLOSSARY.md](GLOSSARY.md) · [CHARTER.md](CHARTER.md) · [STABILITY.md](STABILITY.md) · [CHOICES.md](CHOICES.md) · [CONTRIBUTING.md](CONTRIBUTING.md) | Terms, freeze, how to change |

**Goals:** Cap-only · Ops-only · fail closed · lineage/reverse · Baseline · frozen names.  
**Non-goals:** Ship code, wire-as-law, UI catalogs — see [cek-runtime](https://github.com/bitplorer/cek-runtime).
