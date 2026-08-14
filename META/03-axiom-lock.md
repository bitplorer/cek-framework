# META 03 — Axiom lock

## Rule

Write **non-negotiable laws** before features.  
Features may not relax axioms.  
Axiom change is an explicit charter amendment, not a routine upgrade.

## Why

Implementation pressure always wants:

- “Just trust the session this once.”  
- “Emit this side-effect outside Ops.”  
- “Skip lineage for performance.”  
- “Use the correlation id as permission.”

Axioms exist to make those requests visibly unconstitutional.

## How to write axioms

Each axiom must:

1. Be falsifiable in design review (“does this PR violate A3?”).  
2. Bind *authority*, *effects*, *accountability*, *failure*, *roles*, or *permanence*.  
3. Avoid specifying algorithms (those are L5/L6/L7).

## CEK axiom themes (see CORE for full text)

| Theme | Demand |
|-------|--------|
| Authority | Cap-only truth |
| Effects | Ops-only at kernel boundary |
| Accountability | Lineage when Cap/Activity require it |
| Permanence | Baseline never silent-breaks |
| Failure | Fail closed on authority path |
| Correlation | Trace is not authority |
| Roles | Peer unprivileged |
| Restriction | Attenuation only narrows |
| Composition | Activity/part load is authorized |
| Language | One concept, one name |

## Feature gate

Before accepting a feature:

```text
Does it require violating an axiom?
  yes → reject or amend charter first
  no  → place in correct layer and proceed
```

## Amendment bar

Raising the bar (stricter axiom) is allowed with dual-speak if needed.  
Lowering the bar (weaker authority or weaker accountability) requires explicit rationale and versioning impact analysis.
