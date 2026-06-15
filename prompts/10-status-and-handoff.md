# Status and Handoff

## Use When

Reporting progress to a teammate, reviewer, manager, or another coding agent.

## Required Inputs

- `{{OBJECTIVE}}`
- `{{COMPLETED_WORK}}`
- `{{EVIDENCE}}`
- `{{CURRENT_STATE}}`
- `{{BLOCKERS}}`
- `{{NEXT_ACTION}}`
- `{{RISKS}}`

## Prompt

```text
Prepare a concise engineering status and handoff for this objective:

{{OBJECTIVE}}

Use this structure:

Completed
- {{COMPLETED_WORK}}

Evidence
- {{EVIDENCE}}

Current state
- {{CURRENT_STATE}}

Blockers or decisions needed
- {{BLOCKERS}}

Next action
- {{NEXT_ACTION}}

Residual risk
- {{RISKS}}

Distinguish completed, partially completed, blocked, and unverified work. Name
specific files, task groups, tests, commands, or decisions where useful.
Do not say "done," "production-ready," or "should work" without supporting
evidence.

For a handoff, also include:
- authoritative files to read first;
- branch or commit;
- working-tree state;
- assumptions already verified;
- actions that require approval;
- checks not run and why.
```

## Quality Gate

The recipient should be able to continue without repeating repository
discovery or guessing what remains.

