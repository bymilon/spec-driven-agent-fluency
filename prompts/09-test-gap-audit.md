# Test-Gap Audit

## Use When

Prioritizing missing tests for a repository, feature, migration, or release.

## Required Inputs

- `{{AUDIT_SCOPE}}`
- `{{CRITICAL_BEHAVIORS}}`
- `{{TEST_COMMANDS}}`

## Prompt

```text
Audit test gaps for {{AUDIT_SCOPE}}.

Authoritative context

Read specifications, acceptance criteria, architecture boundaries, incident
history, recent changes, and existing tests. Critical behaviors include:

{{CRITICAL_BEHAVIORS}}

Map existing tests to:
- critical user and business flows;
- state transitions and invariants;
- authorization and security boundaries;
- validation and error handling;
- integration and external-system boundaries;
- migrations, retries, concurrency, and rollback;
- accessibility and supported environments;
- recently changed or historically fragile code.

Rank missing coverage by:
1. impact if the behavior fails;
2. likelihood of failure;
3. change frequency;
4. difficulty of detecting failure before users are affected.

For each finding provide:
- severity and risk;
- untested behavior;
- evidence that coverage is absent or weak;
- production impact;
- smallest high-value recommended test;
- appropriate test level.

Run or inspect:
{{TEST_COMMANDS}}

Do not rank solely by line coverage. Separate missing tests from product or
specification ambiguity.
```

## Quality Gate

The output should be a prioritized risk register, not an unranked wish list of
tests.

