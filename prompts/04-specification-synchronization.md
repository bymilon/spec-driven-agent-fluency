# Specification Synchronization

## Use When

A requirement, architecture decision, or implementation discovery affects
multiple repository artifacts.

## Required Inputs

- `{{CHANGE}}`
- `{{AFFECTED_SPECS}}`
- `{{AFFECTED_CODE}}`
- `{{VALIDATION_COMMANDS}}`

## Prompt

```text
Synchronize the repository with this approved change:

{{CHANGE}}

Affected context

Specifications:
{{AFFECTED_SPECS}}

Implementation:
{{AFFECTED_CODE}}

First trace the change through requirements, plans, code, tests, documentation,
roadmap status, and operational artifacts. Identify contradictions and missing
updates before editing.

Apply the change coherently:
1. update the authoritative decision or requirement;
2. update dependent feature plans and acceptance criteria;
3. update implementation using existing boundaries;
4. add or update tests;
5. update user, operator, migration, or release documentation when affected;
6. update roadmap status only after validation passes.

Preserve traceability from requirement to implementation to test evidence.
Do not mark a phase complete or merge a branch merely because code changes are
present.

Validation

Run:
{{VALIDATION_COMMANDS}}

Report every synchronized artifact, remaining discrepancy, and residual risk.
```

## Quality Gate

Search for stale terminology and superseded behavior after the update. A change
is incomplete when old and new decisions coexist without explanation.

