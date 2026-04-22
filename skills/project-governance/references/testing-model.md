# Testing Model

## Required files before development

```text
docs/testing/acceptance-cases.md
docs/testing/test-strategy.md
```

Optional but recommended:

```text
docs/testing/regression-checklist.md
```

## Testing hierarchy

1. Acceptance tests
   - Product-facing validation
   - Closest to PRD
2. Integration tests
   - Derived from acceptance cases
   - Verify workflow across modules
3. Regression checklist
   - Protects accepted workflows from breakage
4. Unit tests
   - Module/function correctness
   - Written by the feature owner

## Rule

Do not start formal development if acceptance cases are missing.

## Mapping chain

```text
PRD -> spec.md -> acceptance-cases.md -> integration / regression / manual acceptance
```
