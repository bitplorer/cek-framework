# META 06 — Role split (decide vs carry out)

## Rule

Separate **decide** from **carry out**.

- One role verifies authority and establishes truth.  
- The other applies only allowed ordered effects.  
- Neither role absorbs the other.

## Why

When the same component both “is trusted” and “mutates the world freely”:

- Caps become theater.  
- Peers invent truth.  
- Undo and audit lose a single decision point.

## CEK roles

| Role | Name | Duty |
|------|------|------|
| Decide | **Host** | Verify Cap; fail closed; dispatch; record lineage when required; return Result of Ops; project to Baseline when needed |
| Carry out | **Peer** | Apply Ops in order under profile; ignore unknown meta; never mint root Caps; never invent business truth |

## Symmetry notes

- Host and Peer are **roles**, not necessarily “server” and “browser”.  
- Multiple Hosts or Peers may exist; the *law* of the split remains.  
- A process may implement both roles in different boundaries, but each boundary must still obey the split (no Cap-minting inside pure apply path).

## Forbidden collapses

- Peer-issued root Caps.  
- Host emitting free side-effects outside Ops/lineage accounting.  
- “Admin peer” that skips Cap verify by convention without a Cap-gated Host path.
