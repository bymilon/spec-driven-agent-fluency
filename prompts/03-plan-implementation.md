# Plan Implementation

## Use When

An approved feature specification exists and the agent should execute its
remaining task groups.

## Required Inputs

- `{{FEATURE_SPEC_DIRECTORY}}`
- `{{VALIDATION_COMMANDS}}`

## Prompt

```text
Implement the remaining incomplete task groups in
{{FEATURE_SPEC_DIRECTORY}}/plan.md.

Authority

Treat the feature's `requirements.md`, `plan.md`, and `validation.md`, together
with project-level specifications and repository instructions, as authoritative.
Inspect current code and tests before editing.

Execution rules

1. Confirm that the specification is internally consistent.
2. Select the next dependency-ready task group.
3. Implement the smallest coherent change using established repository patterns.
4. Run focused validation for that task group.
5. Update plan status only after its evidence passes.
6. Repeat until all approved groups are complete.
7. Run the broader required validation and inspect the complete diff.

Preserve documented invariants, compatibility requirements, public interfaces,
and unrelated behavior.

Stop conditions

Stop and report if:
- implementation evidence contradicts the specification;
- a required decision is missing;
- a task crosses an unapproved ownership or security boundary;
- migration or rollback behavior is undefined;
- validation cannot run or fails for an unrelated reason;
- completing the task requires expanding scope.

Validation

{{VALIDATION_COMMANDS}}

Completion report

Map completed task groups to requirements and validation evidence. Report
changed files, checks run, checks not run, specification updates, and residual
risk. Do not claim completion while a required task or acceptance criterion
remains open.
```

## Quality Gate

A checked task without passing evidence is not complete.

