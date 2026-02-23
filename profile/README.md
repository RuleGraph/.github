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
- **`lawcards/`** — Registry of versioned LawCards (e.g., gravity.newton.v1) with hashes, signatures, and test vectors. (public soon)
- **`spec/`** — JSON-LD contexts, schemas, and convention docs (IDs, units, validity, invariants, provenance).
- **`benchmarks/`** — Tiny, canonical tasks + acceptance metrics (e.g., 2-body energy drift < 1e-5). (public soon)
- **`examples/`** — Minimal runnable worlds and notebooks. (public soon)

Out of scope (for now): heavy UIs, giant multi-tenant systems, domain-specific apps.

---

## Design Values

- **Small first**: minimal viable spec + passing tests beat grand blueprints.
- **Interchange > implementation**: JSON-LD + Parquet/Zarr preferred over bespoke formats.
- **Safety & clarity**: validity windows and uncertainty are required, not optional.
- **Pluggable**: multiple solvers/engines should produce identical results (within tolerance) from the same dataset.

## Repo Map

- https://github.com/RuleGraph/worldsim-core
- https://github.com/RuleGraph/lawcards (public soon)
- https://github.com/RuleGraph/spec
- https://github.com/RuleGraph/benchmarks (public soon)
- https://github.com/RuleGraph/examples (public soon)

> Prefer short IDs: prefix IRIs with `rg:` (e.g., `rg:law/physics.gravity.newton.v1`). Canonical JSON-LD `@context` will live in `spec/`.

---

## Contributing

1. Open an issue describing the change (bug, feature, LawCard proposal).
2. For specs/LawCards: submit an RFC PR to `spec/` with examples + tests.
3. Ensure all checks pass (`pre-commit`, unit tests).

