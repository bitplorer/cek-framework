# Cap-Effect Meta-Language (CEK)

Locked conceptual charter — the **law** of authorized change across boundaries.

**Start:** [CORE/QUICKSTART.md](CORE/QUICKSTART.md) · **Index:** [INDEX.md](INDEX.md) · **Not CEK:** [KILL-CRITERIA.md](KILL-CRITERIA.md)  
**To implement:** [cek-runtime](https://github.com/bitplorer/cek-runtime)

---

## For developers — what is this?

**CEK is not a library you install and not a language you write apps in.**  
It is a small rulebook for systems where *permission*, *effects*, and *undo* must stay honest.

| Idea | In practice |
|------|-------------|
| **Cap** | Ticket that allows one class of ask |
| **Intent** | The ask |
| **Host** | Checks the ticket, decides, records causes |
| **Ops** | Ordered list of effects (data, not code) |
| **Peer** | Applies that list — does not invent permission |
| **lineage / reverse** | What happened under a Cap/Activity, and how to undo |
| **Baseline** | Classic Ops everyone still understands years later |

**Flow (always the same):**

```text
Host mints Cap → you submit Intent under Cap
→ Host verifies (or refuses with no side effects)
→ Host returns Result with Ops
→ Peer applies Ops
→ when work ends, reverse lineage (or mark non-reversible)
```

### When is CEK useful?

Use this charter when you are building (or reviewing) something that:

- changes a **shared world** (data, devices, multi-agent tools, multiplayer state)  
- must not rely on ambient “admin” or session magic as permission  
- needs **revoke / unload / end** with a defined undo story  
- must **interop** across versions without silent breaks (Baseline)  
- splits **decide** (server, authority service) from **carry out** (UI, agent, device)

### When you do *not* need this repo alone

- You want runnable Host/Peer code, CI vectors, crate layout → use **[cek-runtime](https://github.com/bitplorer/cek-runtime)**  
- You only need a normal app with local state and no cross-boundary authority story  

### How developers use *this* repo

1. Read [CORE/QUICKSTART.md](CORE/QUICKSTART.md) (10 minutes).  
2. Check designs against [KILL-CRITERIA.md](KILL-CRITERIA.md).  
3. Use frozen words only: Cap, Intent, Ops, Host, Peer, Activity, lineage, Baseline.  
4. Implement against the law via [cek-runtime](https://github.com/bitplorer/cek-runtime) (or your own port that passes conformance).

---

| | |
|--|--|
| **Meta** | Fuse explicit parents → partition by intention → lock axioms → name by job → layer strictly → split decide/carry out → require allow/bound/record/reverse → protect Baseline → reject drift → test by canonical speech |
| **Core** | Mint Cap → submit Intent → apply Ops → bound in Activity → record lineage → reverse on end → group with trace → keep Baseline |

## Framework name

Official name: **CEK** (Cap-Effect Meta-Language).  
**Ops** is a kernel noun (ordered carry-out list), not the language name.  
Rejected as official language names: Ops, stylized aliases (e.g. Ceksy, `c+ek`).

## Goals

| Secure | Flexible | Stable |
|--------|----------|--------|
| Cap-only, Ops-only, fail closed, lineage/reverse, Peer unprivileged, Host bootstrap | profile, domain Ops, L6, Activity/part — above the law | Frozen vocabulary, Baseline, dual-speak, conformance |

## Map

| Path | Role |
|------|------|
| [META/](META/) | How the core is derived and amended |
| [CORE/](CORE/) | Language law (00–27) |
| [diagrams/](diagrams/) | Mermaid flows (+ plain tables in READMEs) |
| [PROPOSALS/](PROPOSALS/) | Optional extensions (**not frozen**) |
| [STABILITY.md](STABILITY.md) [GLOSSARY.md](GLOSSARY.md) [STYLE.md](STYLE.md) [CHOICES.md](CHOICES.md) [COMPLETENESS.md](COMPLETENESS.md) [CHARTER.md](CHARTER.md) | Guarantees, terms, style, rationale, audit, freeze |

## Reading order

1. [CORE/QUICKSTART.md](CORE/QUICKSTART.md) + [KILL-CRITERIA.md](KILL-CRITERIA.md)  
2. [CORE/SUMMARY.md](CORE/SUMMARY.md) · [META/SUMMARY.md](META/SUMMARY.md)  
3. Depth as needed (hardening 14–27, scenarios, corners)  
4. [CHARTER.md](CHARTER.md) · optional [PROPOSALS/](PROPOSALS/)  

## Canonical speech

```text
Host mints a Cap.
Caller submits an Intent under that Cap.
Host verifies Cap, records lineage, returns Result with Ops.
Peer applies Ops.
Work is an Activity in a Context; parts load under Caps.
Related Intents share a trace.
When an Activity ends, reverse its lineage.
Everyone supports the Baseline; profile only negotiates apply ability.
```

## Non-goals

Implementation code · wire paths as law · product UI catalogs · marketing renames of kernel terms · implementation languages / crate layout / CI (see [cek-runtime](https://github.com/bitplorer/cek-runtime))
