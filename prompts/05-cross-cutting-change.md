# Cross-Cutting Change

## Use When

Changing a project-wide standard such as testing, security, responsiveness,
logging, accessibility, dependency management, or release workflow.

## Required Inputs

- `{{STANDARD_CHANGE}}`
- `{{DECISION_OWNER}}`
- `{{AFFECTED_AREAS}}`
- `{{MIGRATION_CONSTRAINTS}}`

## Prompt

```text
Evaluate and implement this proposed project-wide standard:

{{STANDARD_CHANGE}}

Decision owner

{{DECISION_OWNER}}

Affected areas

{{AFFECTED_AREAS}}

Before implementation:
1. inventory current standards, tooling, and dependent artifacts;
2. identify compatibility, security, licensing, operational, and training
   impacts;
3. identify decisions requiring approval;
4. propose migration stages, validation, rollback, and deprecation behavior.

Record the approved decision and rationale in the authoritative project
specification or architecture decision record. Propagate it through affected
feature specs, code, tests, tooling, CI, documentation, and contributor
workflows.

Migration constraints

{{MIGRATION_CONSTRAINTS}}

Validate both newly introduced behavior and existing critical behavior.
Do not perform a repository-wide mechanical rewrite without an impact analysis.

Completion report

Report adoption coverage, compatibility results, validation evidence, remaining
legacy usage, rollback readiness, and residual risk.
```

## Quality Gate

A standard is not adopted merely because one configuration file changed.

