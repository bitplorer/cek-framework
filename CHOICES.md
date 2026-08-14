# Design choices — explicit rationale

This file records **why** key choices were made while deriving CEK, so nothing important stays implicit.

## Parent fusion

| Choice | Alternative considered | Why locked |
|--------|------------------------|------------|
| Fuse ux-channel + Cordis only | Add more parents ad hoc | Two parents already cover ask/allow/carry out and bound/undo; more parents without fusion map cause duplicate laws |
| Single law after fusion | Stack frameworks unchanged | Parallel models reintroduce ambient paths |

## Intention set

| Choice | Alternative | Why locked |
|--------|-------------|------------|
| Five intentions + correlate | Open feature list | Open lists create overlapping verbs |
| trace orthogonal | trace as sixth authority mode | Correlation must not grant power |

## Naming

| Choice | Rejected | Why |
|--------|----------|-----|
| Activity | Fiber | Job (bounded work) not obvious with Fiber |
| Baseline | Floor | Permanence not obvious with Floor |
| trace | run, flow, thread, group, related | Collisions or vagueness |
| lineage | history, record | Need authority-linked cause trail, not generic log |
| Cap | token, permission alone | Precision + brevity |
| Ops | effects (as emission noun) | Avoid clash with undo/effect tracking language |
| limit + isolate | attenuate only | Developer-facing verb + structural operation |
| part | plugin | Avoid ambient-load implication |
| mint / submit / apply | run for all | One verb per intention |

## Role split

| Choice | Alternative | Why |
|--------|-------------|-----|
| Host vs Peer | Client/Server names | Topology-independent |
| Peer never mints root Caps | Trusted peer mint | Preserves Cap-only truth |

## Accountability

| Choice | Alternative | Why |
|--------|-------------|-----|
| lineage + reverse required on revocable/endable paths | Best-effort cleanup | Defines unload/revoke |
| Compensation allowed | Inverse only | Real world has irreversible effects |

## Permanence

| Choice | Alternative | Why |
|--------|-------------|-----|
| Baseline permanent | Break freely each release | Decades stability |
| profile negotiates apply only | profile as authority | Authority stays Cap |

## Concept vs wire

| Choice | Alternative | Why |
|--------|-------------|-----|
| Framework names concepts only | Elevate field paths into core | Keeps charter stable across encodings |

## Change

| Choice | Alternative | Why |
|--------|-------------|-----|
| Frozen primary vocabulary | Rename freely | Developers bet on names |
| Conformance as correctness | Docs alone | Executable expectation |
