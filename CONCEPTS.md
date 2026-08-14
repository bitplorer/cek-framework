# Concepts at a glance

Concise pictures of every frozen CEK idea. Full law: [`CORE/`](CORE/). Short defs: [`GLOSSARY.md`](GLOSSARY.md).

**How to read each block:** what it is → where it sits → what it is *not*.

---

## The whole path

```text
mint Cap → submit Intent → Host verify → Result{Ops} → Peer apply
         → Activity bounds work → lineage records causes
         → end/revoke → reverse (or mark non-reversible)
         → trace only groups steps → Baseline always still works
```

---

## Cap

**Permission ticket to submit a class of Intent.**

```text
┌──────── Cap ────────┐
│ action bind         │
│ sealed-args bind    │
│ validity window     │
│ optional: subject,  │
│   scopes, once      │
└─────────────────────┘
        │
   only verified Cap is authority
```

| Is | Is not |
|----|--------|
| Sole authority object at the kernel boundary | Session, TLS identity, “trusted peer”, admin flag |
| Created by **mint** (Host / meta-Cap) | Something Peer invents |

Lifecycle (conceptual): `Minted → Active → Consumed | Expired | Revoked`.

→ [CORE/08](CORE/08-cap.md)

---

## Intent

**The ask** under a Cap.

```text
Intent { action, args, Cap, optional trace }
              │
              ▼
         Host.submit
```

Sealed args cannot be altered by the caller past Cap bind. Open args may fill only what Cap allows.

→ [CORE/21](CORE/21-intent-result-ops.md) · [CORE/22](CORE/22-sealed-args.md)

---

## Host

**Role that decides.** Verifies Cap, dispatches, records lineage, projects Ops, reverses.

```text
┌──────────── Host ────────────┐
│ mint · verify · once/idem    │
│ dispatch · lineage · project │
│ reverse · Result             │
└──────────────────────────────┘
```

| Does | Does not |
|------|----------|
| Own truth and permission | Rely on Peer to “confirm” Cap |
| Fail closed on bad Cap | Emit mutate Ops after refuse |

→ [CORE/06](CORE/06-host-peer.md)

---

## Peer

**Role that carries out.** Applies Ops under a profile only.

```text
┌──────────── Peer ────────────┐
│ profile · apply Ops in order │
│ optional receipt             │
│ NO mint · NO Cap authority   │
└──────────────────────────────┘
```

| Does | Does not |
|------|----------|
| Apply data-only Ops | Mint root Caps |
| Report landed/failed | Invent business truth |

→ [CORE/06](CORE/06-host-peer.md)

---

## Ops

**Ordered list of effects as data** (not code, not callbacks).

```text
Result.ops = [ Op{ ns, name, payload }, … ]
                 │
                 ▼
            Peer.apply in order
```

Only way shared-world effects leave the Host decision boundary.

→ [CORE/21](CORE/21-intent-result-ops.md)

---

## Result

**Host’s answer to an Intent.**

```text
Result
  ok                 → ops[]
  authority_refusal  → zero mutate ops (Cap failed)
  dispatch_error     → after verify, handler/policy miss
```

Callers must not treat refusal like a normal business miss.

→ [CORE/21](CORE/21-intent-result-ops.md)

---

## Activity & Context

**Activity** = bounded job with a lifetime (can end → reverse).  
**Context** = what that job may see/use (mediated, not ambient power).

```text
┌────── Activity ──────┐
│ lifetime · lineage   │
│ ends → reverse       │
│   Context (visibility)│
│   parts (Cap-gated)  │
└──────────────────────┘
```

| Verb | Job |
|------|-----|
| **inject** | Declare what Activity needs |
| **limit** | Narrow what may be seen/done |
| **isolate** | Separate a Context slice |
| **part** | Composition unit loaded under Cap |

limit/isolate only **narrow** (never widen).

→ [CORE/07](CORE/07-activity-context.md)

---

## lineage & reverse

**lineage** = cause trail under Cap/Activity.  
**reverse** = undo that trail on end/revoke (or mark non-reversible).

```text
Cap ok + work happens
        │
        ▼
   lineage entry
   (authorized Ops + reverse plan)
        │
   Activity end / Cap revoke
        │
        ▼
   reverse: inverse | compensation | non_reversible mark
```

Completing an apply (e.g. DOM morph) does **not** auto-reverse.

→ [CORE/09](CORE/09-lineage-reverse.md)

---

## authorized set vs landed set

```text
Host Result.ops     = authorized set   (what was allowed)
Peer actually applied = landed set     (what stuck)

receipt present?  → reverse prefers landed
no receipt?       → reverse uses authorized
```

**apply receipt** = Peer report of landed/failed — **not** a Cap.

→ [CORE/25](CORE/25-landed-and-receipts.md)

---

## trace

**Correlation only** across related Intents.

```text
trace_id ── groups steps ── does NOT grant Cap
Each step still needs its own verified Cap.
```

→ [CORE/10](CORE/10-trace.md)

---

## Baseline & profile

```text
Baseline = permanent classic Ops everyone still understands
profile  = what this Peer can apply (richer or equal)

Host projects: profile ∩ ability ∪ Baseline fallback
profile never grants Cap authority
```

→ [CORE/11](CORE/11-baseline-profile.md)

---

## idempotency bind

Optional: same logical ask → one cause / one Result digest on retry.  
Checked on Host **before** side effects when required.

→ [CORE/26](CORE/26-idempotency.md)

---

## recovery Cap

Narrow Cap used only to submit **compensation** during reverse when inverse Ops are not enough.

Still a real Cap — full verify, not a back door.

→ [CORE/27](CORE/27-recovery-cap.md)

---

## Layers (where concepts live)

```text
L0  Law (axioms, vocabulary)
L1  Host / Peer kernels
L2  Activity · Context · lineage
L3  trace
L4  profile
L5  domain drivers / Op namespaces
L6  policy (must not relax axioms)
L7  application
```

→ [CORE/05](CORE/05-layers.md)

---

## Verbs (jobs)

| Verb | Job |
|------|-----|
| **mint** | Create Cap |
| **submit** | Send Intent under Cap |
| **apply** | Carry out Ops |
| **reverse** | Undo lineage / end cleanly |
| **inject / limit / isolate** | Shape Activity Context |

One concept, one name — no synonym fork.

---

## Defaults when unsure

| Situation | Do |
|-----------|-----|
| Authority unclear | Refuse |
| Unknown optional meta | Ignore |
| Peer can’t do rich Ops | Lower to Baseline |
| Undo impossible | Mark non-reversible; don’t fake success |
| Multi-step group | trace (still Cap each step) |

→ [KILL-CRITERIA.md](KILL-CRITERIA.md) · [CORE/QUICKSTART.md](CORE/QUICKSTART.md)

---

## Implementation

How Host/Peer processes, contract, and wire fit together:  
**[cek-runtime CONCEPTS](https://github.com/bitplorer/cek-runtime/blob/main/CONCEPTS.md)** · **[TOPOLOGY](https://github.com/bitplorer/cek-runtime/blob/main/TOPOLOGY.md)**
