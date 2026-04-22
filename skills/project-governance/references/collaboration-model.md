# Collaboration Model

## Default mode

Use **dual-owner delivery** by default:

- one feature owner
- one test owner

## Feature owner responsibilities

- implement the feature
- write unit tests
- do local developer self-test
- keep changes inside assigned module boundary

## Test owner responsibilities

- implement acceptance/integration checks from `acceptance-cases.md`
- maintain regression checklist
- validate from end-user perspective
- avoid becoming a second feature implementer by default

## Leo responsibilities

- split tasks
- freeze boundaries
- bind each task to spec sections and acceptance IDs
- integrate and accept

## Jack responsibilities

- architecture review
- hard bug support
- difficult system design only

## Important constraint

Do not assign two agents to write the same core implementation simultaneously unless interfaces are already frozen and boundaries are explicit.
