# CORE 24 — Moving parts and missing corners

How CEK stays **stable** when pieces move, and **complete** when knowledge is incomplete.

---

## 1. Two kinds of incompleteness

| Kind | Meaning | Danger if ignored |
|------|---------|-------------------|
| **Moving parts** | Things allowed to evolve (profiles, domain Ops, L7, L6 policy, encodings) | Treated as kernel law → churn and breaks |
| **Missing corners** | Edge cases not yet specialized (partial apply, irreversible effects, store down, multi-Peer, clock skew) | Improvised ambient escapes |

The framework does **not** pretend every corner is implemented.  
It **does** require every corner to fall into a **defined default behavior** that preserves axioms.

---

## 2. Doctrine: fixed law, mobile surface

```text
FIXED (must not drift)
  axioms · vocabulary · Host/Peer split · Cap-only · Ops-only
  lineage/reverse obligation · Baseline · fail closed · trace ≠ authority

MOBILE (may move without charter amendment)
  domain Ops · profiles · L6 policy · L7 product · Cap encoding
  transports · optional receipts/idempotency · driver quality
```

**Rule:** When something moves, it moves **above** L2 or in encoding — never by silently redefining Intent, Cap, or Baseline.

---

## 3. Default behaviors for missing corners

Every incomplete corner maps to one of:

| Default | When used |
|---------|-----------|
| **Refuse (fail closed)** | Authority uncertain, once-store down, required lineage cannot be written |
| **Ignore (safe)** | Unknown optional meta; unknown Ops under Baseline-tolerant profile |
| **Lower (project)** | Rich outcome → Baseline Ops the Peer can apply |
| **Mark (honest)** | Reverse cannot complete → non-reversible mark + audit, not fake success |
| **Bound (time/scope)** | Activity end / Cap revoke → reverse what was recorded |
| **Defer to profile** | Strict vs tolerant unknown-Ops; stop vs continue on partial apply |

No fourth path of “just this once ambient allow.”

---

## 4. Corner catalog (closed defaults)

### Authority

| Corner | Default |
|--------|---------|
| Cap missing when required | Refuse |
| Cap integrity/action/sealed-args fail | Refuse |
| Single-use replay | Refuse |
| Once-store unavailable and once required | Refuse |
| Bootstrap | Host-only, minimal, explicit — never Peer |

| Idempotent retry (if bind present) | Host dedupe before lineage; store down + bind required → refuse |
| Apply receipt absent | Reverse uses Host-authorized Ops set |
| Apply receipt present | Reverse prefers landed set; receipt ≠ Cap |

### Effects

| Corner | Default |
|--------|---------|
| Unknown Op (tolerant profile) | Ignore or soft-fail |
| Unknown Op (strict profile) | Reject Result path per policy; no kernel crash |
| Empty Ops on success | Allowed (pure decision, no carry-out) |
| Peer cannot apply subset | Partial-apply policy; do not invent Host truth |

### Composition / undo

| Corner | Default |
|--------|---------|
| Activity ends | Reverse lineage |
| Cap revoked | Reverse lineage tied to that Cap (policy may scope) |
| No true inverse | Compensation under recovery Cap, or mark non-reversible |
| Observe-only Ops | May omit from mutate lineage if classed observe (when P2 adopted); else treat as mutate |

### Correlation

| Corner | Default |
|--------|---------|
| No trace | Fine — single-step |
| Trace without Cap | Still no permission |
| Resume after expiry | Fresh Caps required; trace does not revive Cap |

### Interop

| Corner | Default |
|--------|---------|
| Peer has no profile | Baseline projection |
| Host speaks richer law | Dual-speak / Baseline still accepted during window |
| Optional meta unknown | Ignore |

### Concurrency / time

| Corner | Default |
|--------|---------|
| Concurrent single-use Cap | At most one consume wins |
| Concurrent Activities | Separate lineage unless L6 defines joint reverse |
| Clock skew on Cap expiry | Fail closed on verify if outside window under Host clock policy |
| Abandoned Activity | End → reverse (optional time-box policy) |

---

## 5. How moving parts are allowed to move

| Moving part | Stable interface | Change mechanism |
|-------------|------------------|------------------|
| Domain Ops | Ordered Ops data; profile advertise | Add namespace; provide Baseline lowering |
| profile | Declares apply ability only | Revision; intersection with Host |
| L6 policy | Cannot bypass Cap verify | Optional; Host-enforced |
| L7 handlers | Must submit Intent under Cap | App deploy |
| Cap encoding | Conceptual binds fixed | Crypto/format agility behind verify |
| Transport | Delivers Intent/Result | Replace freely |
| PROPOSALS features | Optional until adopted | CORE/12 + conformance |

---

## 6. Completeness definition (operational)

The framework is **complete** when:

1. Every kernel concept maps to an intention (or correlation).  
2. Every axiom has testable consequences.  
3. Every known corner has a **default** in §4.  
4. Every moving part has a **stable interface** in §5.  
5. Unknown future features have a **placement rule** (layer + speech test + no axiom relax).  

It is **not** incomplete merely because:

- a domain Op catalog is unfinished,  
- an implementation is missing,  
- or a PROPOSAL is not adopted.

---

## 7. Handling new corners later

When a new edge case appears:

```text
1. Can it be handled by an existing default (refuse / ignore / lower / mark / bound / profile)?
   → Document under this file; no charter change.
2. Does it need new optional policy only?
   → L6 / profile; Baseline ignore path.
3. Does it change meaning of Cap, Intent, Ops, Activity, lineage, or Baseline?
   → Major law version + dual-speak + charter.
4. Does it create ambient authority or free effects?
   → Reject.
```

---

## 8. Stability under motion (summary)

| Pressure | Response |
|----------|----------|
| Feature velocity | Mobile surface L4–L7 only |
| Unknown Peer | Baseline projection |
| Unknown meta/Ops | Ignore or profile policy |
| Authority doubt | Refuse |
| Undo doubt | Mark non-reversible; never lie |
| Multi-step | trace groups; Cap still per step |
| Evolution of meaning | Version; do not silent-shift names |

---

## 9. One-line doctrine

**Freeze the law; default every corner; let only the surface move — and when it moves, lower to Baseline or refuse, never ambient-allow.**
