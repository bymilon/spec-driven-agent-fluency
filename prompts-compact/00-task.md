# Task

```text
OBJ: {{OBJECTIVE}}
AUTH: read {{FILES}}; inspect code/tests; facts != assumptions.
SCOPE+: {{IN_SCOPE}}
SCOPE-: {{OUT_SCOPE}}
RULES: {{CONSTRAINTS}}; preserve API/invariants/unrelated behavior; no deps unless approved.
DO: reproduce -> smallest coherent patch -> focused tests -> full required checks -> diff review.
STOP: spec conflict / missing product-security-data decision / destructive action / validation unavailable / scope expansion.
VERIFY: {{COMMANDS}}
DONE: {{ACCEPTANCE}}
OUT: cause; files; behavior; checks pass/fail/not-run; residual risk.
```

