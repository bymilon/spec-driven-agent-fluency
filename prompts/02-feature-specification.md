# Feature Specification

## Use When

Converting an approved roadmap phase or product request into implementation-ready
requirements, plan, and validation artifacts.

## Required Inputs

- `{{ROADMAP_FILE}}`
- `{{PROJECT_SPECS}}`
- `{{FEATURE_NAME}}`
- `{{SPEC_DIRECTORY}}`

## Prompt

```text
Prepare the feature specification for {{FEATURE_NAME}}.

Context

Read {{ROADMAP_FILE}}, {{PROJECT_SPECS}}, relevant existing feature specs, and
the current implementation. Identify the roadmap outcome this feature serves.

Clarification

Before writing files, interview me about:
1. user behavior, success outcome, and failure behavior;
2. included scope, exclusions, compatibility, and migration;
3. architecture constraints, security, data, observability, and acceptance
   evidence.

Call out assumptions and conflicts. Do not silently choose unresolved product or
architecture behavior.

Artifacts

Create {{SPEC_DIRECTORY}}/{{FEATURE_NAME}}/ containing:

- `requirements.md`
  - user outcome and behavior;
  - scope and explicit exclusions;
  - interfaces, data, errors, and edge cases;
  - security, privacy, accessibility, and operational requirements;
  - approved decisions and unresolved questions.

- `plan.md`
  - ordered numbered task groups;
  - dependencies and ownership boundaries;
  - migration and rollback work when applicable;
  - validation associated with each task group.

- `validation.md`
  - acceptance criteria mapped to requirements;
  - focused, integration, end-to-end, and manual checks as applicable;
  - exact commands;
  - merge preconditions;
  - residual risks requiring approval.

Validation

Check that every requirement has implementation work and acceptance evidence.
Check that all three documents agree. Do not implement until unresolved
decisions are approved.
```

## Quality Gate

Requirements describe behavior. The plan describes work. Validation describes
evidence. Do not mix these responsibilities.

