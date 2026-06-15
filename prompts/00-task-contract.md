# Task Contract

## Use When

You need a general-purpose prompt for a bounded feature, defect, refactor, or
documentation task.

## Required Inputs

- `{{OBJECTIVE}}`
- `{{AUTHORITATIVE_FILES}}`
- `{{IN_SCOPE}}`
- `{{OUT_OF_SCOPE}}`
- `{{CONSTRAINTS}}`
- `{{VALIDATION_COMMANDS}}`
- `{{ACCEPTANCE_CRITERIA}}`

## Prompt

```text
Objective

{{OBJECTIVE}}

Authoritative context

Read {{AUTHORITATIVE_FILES}} before making changes. Inspect the current
implementation and tests relevant to this task. Distinguish repository facts
from assumptions.

Scope

In scope:
{{IN_SCOPE}}

Out of scope:
{{OUT_OF_SCOPE}}

Constraints

{{CONSTRAINTS}}

Preserve unrelated behavior, public interfaces, and repository conventions.
Do not introduce new dependencies unless they are required and approved.

Execution

1. Reproduce or confirm the current behavior.
2. Identify the smallest coherent change.
3. Implement it using existing repository patterns.
4. Add or update focused validation.
5. Inspect the final diff for unrelated changes.

Stop conditions

Stop and report before proceeding if:
- authoritative artifacts contradict each other;
- a product, security, data, or architecture decision is missing;
- the task requires an irreversible operation;
- required validation cannot run;
- the necessary change exceeds the stated scope.

Validation

Run:
{{VALIDATION_COMMANDS}}

Acceptance criteria

{{ACCEPTANCE_CRITERIA}}

Completion report

Summarize:
- the observed root cause or starting state;
- files and behavior changed;
- validation results;
- checks not run and why;
- residual risks or unresolved decisions.
```

## Quality Gate

Do not accept a completion claim that says only "done" or "should work."
Require observable evidence.

