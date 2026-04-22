# Software Development Rules v0.1

## Rule 1 — PRD → Spec Governance
- GitHub is the canonical logical source of truth.
- Each project has one canonical repo and one canonical spec at `docs/specs/spec.md`.
- Development starts only after spec status is `frozen`.

## Rule 2 — Project Directory Management
- Keep repo root minimal.
- Planning/architecture/task docs belong in `docs/`.
- Runtime data must live outside the repo in each agent's sandbox workspace-data.
- Avoid long-lived sibling directories such as `-v2`, `-new`, `-final`, `-repo`, `-spec`.

## Rule 3 — Testing Before Development
- Create `docs/testing/acceptance-cases.md` before formal development.
- Create `docs/testing/test-strategy.md` for non-trivial projects.
- Acceptance cases are the upper-layer source of truth for integration and regression tests.
- Unit tests belong to the feature owner.

## Rule 4 — Collaboration Model
- Default model: one feature owner + one test owner.
- Feature owner writes implementation and unit tests.
- Test owner writes acceptance/integration/regression checks.
- Do not assign two agents to write the same core implementation simultaneously unless boundaries are frozen.

## Rule 5 — Git Policy
- Long-lived branches: `main`, `features`.
- Developers branch from `features`.
- Before push: sync latest `features`, run relevant checks, then push.
- Merge `features` into `main` only when Aaron decides.
