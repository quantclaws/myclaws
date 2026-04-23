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

## Rule 6 — Sync Checkpoints
- Feature owner must commit code before cross-agent verification.
- Test owner must verify against a synced sandbox copy of the same Git baseline, not another agent's local directory.
- Minimum checkpoints:
  1. spec freeze
  2. feature-owner green commit
  3. test-owner synced verification pass
  4. closeout commit / merge-ready snapshot

## Rule 7 — Requirement Change Governance
- New requirements may refine, supersede, or invalidate earlier requirements.
- On every new requirement, the first step is mandatory recall:
  1. search memory
  2. inspect canonical docs / PRD / spec / ADR / tasks
  3. compare the new request against the currently frozen understanding
- If the new requirement overlaps an existing one, Leo must explicitly ask/confirm whether it:
  - clarifies the old requirement
  - partially overrides it
  - fully replaces it
- Once a replacement/override is confirmed, stale requirements must be marked invalid in docs/tasks/status rather than silently coexisting.
- If the change affects architecture, workflow, acceptance criteria, or core prompts, document updates come before further feature work.
- If active development is proceeding on assumptions invalidated by the new requirement, pause or redirect that development first, then update docs/spec/tasks, then resume coding.
- Goal: PRD, spec, tasks, and code must converge continuously; do not allow drift across iterations.
