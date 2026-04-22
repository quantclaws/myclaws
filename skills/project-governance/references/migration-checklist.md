# Project Cleanup / Migration Checklist

## Classify each existing path

- canonical repo
- runtime data
- experimental copy
- obsolete copy
- archive-only docs

## Move docs into docs/

- root planning docs -> `docs/tasks/` or `docs/archive/`
- architecture docs -> `docs/adr/` or `docs/architecture/`
- PRD -> `docs/prd/`
- spec -> `docs/specs/spec.md`

## Move runtime outputs out of repo

- `logs/`
- `tmp/`
- screenshots
- exports
- crawled content
- local sqlite files
- browser/session state

## Remove naming drift

Long-lived sibling directories like below should be merged, archived, or deleted:
- `project-v2`
- `project-new`
- `project-final`
- `project-repo`
- `project-spec`

## Final deliverable

Produce a table with:
- path
- classification
- action (`keep`, `move`, `archive`, `delete`)
- rationale
