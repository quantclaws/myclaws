---
name: project-governance
description: Use when receiving a new PRD, defining software project rules, creating or freezing spec.md, designing testing strategy, assigning multi-agent development roles, cleaning up messy project folders, or deciding canonical repo / docs / workspace / git structure for sandboxed multi-agent development. Covers PRD intake, spec governance, GitHub as canonical source, per-agent workspace copies, test-first planning, dual-owner collaboration, and branch policy.
---

# Project Governance

Use this skill **before coding starts** for any new software project, and when auditing a messy repo that already exists.

## Core rules

1. **GitHub is the logical single source of truth**
   - Every project has one canonical GitHub repo.
   - Physical directories may differ per agent; logical truth must not.

2. **Each agent works only in its own sandbox workspace**
   - Default project path: `agents/<agent>/workspace/projects/<repo-name>/`
   - Runtime data lives outside the repo: `agents/<agent>/workspace-data/<repo-name>/`
   - Leo / Jack may inspect broader paths for debugging, but their default project path is still `agents/<agent>/workspace/`.

3. **One canonical spec**
   - Canonical spec path: `docs/specs/spec.md`
   - PRD is archived separately under `docs/prd/`
   - Development starts only after spec status becomes `frozen`.

4. **Root directory stays minimal**
   - Root may contain: `README`, package/build files, `docs/`, `app|src/`, `tests/`, `scripts/`, `config/`, `fixtures/`.
   - Planning / architecture / task docs must not live in root.

5. **No parallel pseudo-project directories**
   - Forbidden long-lived names: `-v2`, `-new`, `-final`, `-repo`, `-spec` at the same level as the main project.
   - Experiments must use git branches, worktrees, `experiments/`, or `docs/archive/`.

6. **Testing is defined before development starts**
   - Every non-trivial project needs:
     - `docs/testing/acceptance-cases.md`
     - `docs/testing/test-strategy.md`
   - Acceptance cases are the upper-layer source of truth for integration and regression tests.
   - Unit tests belong to the feature owner.

7. **Default collaboration model is dual-owner**
   - One owner builds the feature.
   - One owner builds/maintains acceptance, integration, and regression tests.
   - Do not assign two agents to write the same core implementation at the same time.

8. **Git policy is simple and explicit**
   - Primary long-lived branches: `main`, `features`
   - Developers branch from `features`
   - Merge `features` into `main` only when Aaron decides.

## Workflow when a new PRD arrives

1. Create a project card with:
   - project name
   - goal
   - scope / out-of-scope
   - acceptance criteria
   - decision owner
   - current status (`PRD/raw`, `spec/draft`, `spec/frozen`, `in-dev`, `qa`, `accepted`)
2. Create or identify the canonical GitHub repo.
3. Create the canonical doc set:
   - `docs/prd/PRD-v1.md`
   - `docs/specs/spec.md`
   - `docs/tasks/task-breakdown.md`
   - `docs/testing/acceptance-cases.md`
   - `docs/testing/test-strategy.md`
4. Collect team review notes.
   - Leo owns scope and freeze decisions.
   - Ryan / Jack review architecture and risk.
   - Devon reviews implementation order and effort.
   - Muse reviews IA / UX / content-facing structure when relevant.
5. Freeze `docs/specs/spec.md` and acceptance cases before development begins.
6. Assign owners per task:
   - feature owner
   - test owner
   - linked spec section
   - linked acceptance case IDs

## Testing policy

Use the hierarchy below:

1. **Acceptance tests**
   - Closest to PRD and final user behavior
   - Defined in `docs/testing/acceptance-cases.md`
2. **Integration tests**
   - Derived from acceptance cases
   - Verify full workflow across modules
3. **Regression checklist**
   - Protects previously accepted workflows
4. **Unit tests**
   - Written by the feature owner for module-level correctness

Do not start formal development if acceptance cases are missing.

## Collaboration policy

Default mode: **one feature owner + one test owner**.

- Feature owner:
  - implements business logic
  - writes unit tests
  - performs local developer self-test
- Test owner:
  - translates acceptance cases into integration / acceptance checks
  - maintains regression checklist
  - validates behavior from final-user perspective
- Leo:
  - defines task boundaries
  - binds work to spec sections and acceptance IDs
  - integrates and accepts
- Jack:
  - only for difficult architecture, hard bugs, or early design review

Only use parallel feature development when boundaries are frozen and interfaces are explicit.

## Git policy

1. Canonical repo lives on GitHub.
2. Long-lived branches:
   - `main`
   - `features`
3. Developers create personal branches from `features`, for example:
   - `devon/subscription-panel`
   - `ryan/acceptance-tests-subscription-panel`
4. Before pushing a finished branch:
   - merge or rebase the latest `features`
   - run local regression / acceptance checks
   - then push
5. Merge direction:
   - personal branch -> `features`
   - `features` -> `main` only when Aaron approves
6. Avoid `release`, `fix`, `final`, `v2` branch habits unless Aaron explicitly asks.

## Workflow when auditing an existing messy project

1. Identify the canonical repo directory.
2. Classify every extra folder as one of:
   - canonical repo
   - runtime data
   - experimental copy
   - obsolete archive
3. Merge docs into `docs/`.
4. Move runtime outputs out of repo.
5. Archive or delete pseudo-project directories.
6. Reconstruct acceptance cases if they are missing.
7. Write the cleanup decision into memory.

## Required references

Read these references when needed:
- For repo structure: `references/repo-layout.md`
- For spec fields: `references/spec-template.md`
- For testing design: `references/testing-model.md`
- For collaboration split: `references/collaboration-model.md`
- For branch policy: `references/git-policy.md`
- For cleanup / migration: `references/migration-checklist.md`

## Output expectations

When using this skill, produce:
1. canonical repo name
2. canonical spec path
3. recommended repo tree
4. testing deliverables and owner split
5. branch plan
6. items to merge / archive / delete
7. explicit blockers needing Aaron to decide
