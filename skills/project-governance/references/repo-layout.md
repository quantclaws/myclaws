# Recommended Repo Layout

```text
project-name/
├── README.md
├── .gitignore
├── Makefile
├── pyproject.toml / package.json / requirements.txt
├── docs/
│   ├── prd/
│   ├── specs/
│   │   ├── spec.md
│   │   ├── spec-history/
│   │   └── open-questions.md
│   ├── tasks/
│   ├── adr/
│   ├── testing/
│   └── archive/
├── app/ or src/
├── tests/
│   ├── unit/
│   ├── integration/
│   ├── e2e/
│   └── fixtures/
├── scripts/
├── config/
├── fixtures/
└── tmp/   # gitignored
```

## Outside repo per agent

```text
agents/<agent>/workspace/projects/<repo-name>/      # git working copy
agents/<agent>/workspace-data/<repo-name>/          # runtime data, logs, exports, cache
```

## Keep out of repo root

- execution plans
- architecture drafts
- task assignment notes
- prompt scratch docs
- screenshots
- exports
- logs
- caches
- temporary HTML or markdown renders
