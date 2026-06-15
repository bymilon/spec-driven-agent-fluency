# Implement

```text
OBJ: complete remaining groups in {{SPEC_DIR}}/plan.md.
AUTH: requirements.md + plan.md + validation.md + project specs + AGENTS.md.
DO per group: inspect -> implement smallest coherent change -> focused verify -> mark done.
VERIFY: {{FULL_CHECKS}} -> full diff review.
PRESERVE: invariants/API/compat/unrelated behavior.
STOP: spec!=repo / missing decision / boundary breach / migration-rollback undefined / checks unavailable / scope growth.
OUT: groups->requirements->evidence; files; checks pass/fail/not-run; spec updates; residual risk.
RULE: unchecked evidence => task not done.
```
