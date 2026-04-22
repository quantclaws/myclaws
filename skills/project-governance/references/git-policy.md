# Git Policy

## Canonical source

GitHub is the canonical source of truth.

## Long-lived branches

- `main`
- `features`

## Personal working branches

Create from `features`, for example:

- `devon/subscription-panel`
- `ryan/acceptance-tests-subscription-panel`
- `muse/editor-ux-copy`

## Merge policy

1. personal branch -> `features`
2. `features` -> `main` only when Aaron approves

## Before pushing

- sync latest `features`
- run local acceptance / regression checks relevant to the task
- then push

## Avoid by default

- `release/*`
- `fix/*`
- `final/*`
- `v2/*`

Only add extra branch types if Aaron explicitly asks.
