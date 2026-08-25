# Contributing

This repository is a **conceptual freeze** (law), not application code.

## Editorial (no amendment)

- Clarity that does not change meaning  
- New conformance *vectors* that test existing law  
- Drafts under `PROPOSALS/`  
- Reader-path text under `docs/` (map only; CORE remains authority)  

Follow [STYLE.md](STYLE.md). Prefer pointers in hub docs; keep power in CORE detail files.

If `docs/` and CORE diverge, **CORE wins**.

## Law change (charter amendment)

See [CHARTER.md](CHARTER.md):

1. Canonical speech — [META/10](META/10-canonical-speech-test.md)  
2. Layer + change class — [CORE/12](CORE/12-change-law.md)  
3. Axiom / naming / Baseline check  
4. [CORE/18](CORE/18-invariants.md) + [CORE/19](CORE/19-conformance.md)  
5. Log the amendment in CHARTER  

## Implementation

Host/Peer design, crates, CI, isolation → **[cek-runtime](https://github.com/bitplorer/cek-runtime)** and **[cek-python](https://github.com/bitplorer/cek-python)**.  
L5 domain apply (e.g. hardware) → **[cek-hw](https://github.com/bitplorer/cek-hw)** — not a Host kernel.  
Do not land Rust layout or language-specific APIs in this repo.
