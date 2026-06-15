# Multi-Perspective Review

## Use When

Reviewing a feature branch, pull request, migration, or release candidate with
multiple agents or reviewers.

## Required Inputs

- `{{REVIEW_TARGET}}`
- `{{AUTHORITATIVE_REQUIREMENTS}}`
- `{{RISK_PROFILE}}`
- `{{VALIDATION_EVIDENCE}}`

## Prompt

```text
Review {{REVIEW_TARGET}} against {{AUTHORITATIVE_REQUIREMENTS}}.

Risk profile

{{RISK_PROFILE}}

Validation already available

{{VALIDATION_EVIDENCE}}

Use independent review lenses:

1. Requirements and behavior
   - requirement mismatches;
   - edge cases and failure behavior;
   - compatibility and user impact.

2. Architecture and maintainability
   - boundary violations;
   - unnecessary complexity;
   - unsafe coupling, concurrency, or data behavior.

3. Validation and operations
   - missing or weak tests;
   - security and accessibility risks;
   - observability, deployment, migration, and rollback gaps.

For every finding provide:
- severity: blocker, high, medium, or low;
- precise problem;
- file and evidence;
- impact and affected users or systems;
- concrete recommended correction.

Do not report unsupported style preferences as defects. Consolidate duplicate
findings and identify disagreements between reviewers. Lead the final report
with findings ordered by severity, followed by open questions and residual
risk.
```

## Quality Gate

More reviewers do not create quality unless their scopes, evidence standards,
and final accountability are explicit.

