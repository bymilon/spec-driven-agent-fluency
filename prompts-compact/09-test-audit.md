# Test Audit

```text
SCOPE: {{AUDIT_SCOPE}}
AUTH: specs/criteria/incidents/recent diff/current tests.
MAP tests -> {{CRITICAL_BEHAVIORS}} + states/invariants/auth/errors/integrations/migrations/retries/concurrency/a11y.
RANK gap = impact * likelihood * change-frequency * detection-difficulty.
FINDING: severity; untested behavior; evidence; prod impact; smallest valuable test; test level.
CHECK: {{TEST_COMMANDS}}
NO: line coverage as sole signal; unranked test wishlist.
SEPARATE: missing test vs missing requirement.
STOP: critical behavior undefined / test evidence unavailable / scope ambiguous.
OUT: risk-ranked gaps + recommended order.
```
