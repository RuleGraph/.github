# RuleGraph

**Open standards for Rules as Data (LawCards)**  
RuleGraph unifies **rules (“LawCards”)**, **typed state (with units & uncertainty)**, and **graph links** so any solver or agent can reason, simulate, and explain with **provenance and invariants**.

---

## Mission

Advance an open, solver-agnostic stack that makes simulations:
- **Declarative**: laws as data, not buried in code
- **Verifiable**: units, validity ranges, and invariants by design
- **Linked**: JSON-LD graphs across domains and scales
- **Reproducible**: content-addressed artifacts, signatures, and lockfiles

We start small (classical mechanics demo) and grow by **LawCards + specs** others can reuse.

---

## Scope (what lives under this org)

- **`worldsim-core/`** — Python kernel: load/validate JSON-LD worlds, resolve LawCards, bind solvers, run steps, audit invariants.
- **`lawcards/`** — Registry of versioned LawCards (e.g., gravity.newton.v1) with hashes, signatures, and test vectors.
- **`spec/`** — JSON-LD contexts, schemas, and convention docs (IDs, units, validity, invariants, provenance).
- **`benchmarks/`** — Tiny, canonical tasks + acceptance metrics (e.g., 2-body energy drift < 1e-5).
- **`examples/`** — Minimal runnable worlds and notebooks.

Out of scope (for now): heavy UIs, giant multi-tenant systems, domain-specific apps.

---

## Design Values

- **Small first**: minimal viable spec + passing tests beat grand blueprints.
- **Interchange > implementation**: JSON-LD + Parquet/Zarr preferred over bespoke formats.
- **Safety & clarity**: validity windows and uncertainty are required, not optional.
- **Pluggable**: multiple solvers/engines should produce identical results (within tolerance) from the same dataset.

---

## Governance

- **Model**: lightweight maintainer model (initial BDFL → maintainers group as contributors join).
- **Decisions**: public issues + RFCs in `spec/` via PRs. We seek rough consensus + passing tests.
- **Releases**: SemVer for code, calendar tags for specs; LawCards versioned as `name.major.minor` (e.g., `gravity.newton.v1`).
- **Security**: report privately via GitHub Security Advisories on the affected repo.
- **Code of Conduct**: Contributor Covenant v2.1 (applies org-wide).
- **License**: Apache-2.0 for code and specs; LawCards published under CC-BY-4.0 + attached hashes/signatures.

---

## Roadmap (initial)

- **v0.1**
  - `worldsim-core`: loaders, validators (units/validity), solver registry, simple Verlet, invariant watchdog, lockfile
  - `lawcards`: `gravity.newton.v1` with test vectors + drift budgets
  - `spec`: contexts for `gw:` IDs, units (QUDT), PROV, LawCard fields
  - `benchmarks`: Earth–Sun 1-year run @60s dt, energy drift < 1e-5

- **v0.2**
  - Post-Newtonian switch & regime detection
  - Parquet/Zarr guidance, reproducibility how-to
  - Cross-engine reproducibility demo

---

## Repo Map

- https://github.com/RuleGraph/worldsim-core
- https://github.com/RuleGraph/lawcards
- https://github.com/RuleGraph/spec
- https://github.com/RuleGraph/benchmarks
- https://github.com/RuleGraph/examples

> Prefer short IDs: prefix IRIs with `rg:` (e.g., `rg:law/gravity.newton.v1`). Canonical JSON-LD `@context` will live in `spec/`.

---

## Contributing

1. Open an issue describing the change (bug, feature, LawCard proposal).
2. For specs/LawCards: submit an RFC PR to `spec/` with examples + tests.
3. Ensure all checks pass (`pre-commit`, unit tests).
4. Be kind; follow the CoC.

**Good first issues** are labeled across repos.

---

## Citation

If this work helps your research/product, please cite the org and the specific LawCard used. Example `CITATION.cff` entries live in each repo.

---

## Maintainers

- Lead: Francis Bousquet (founder)
- Maintainers: (TBD — seeking contributors)

