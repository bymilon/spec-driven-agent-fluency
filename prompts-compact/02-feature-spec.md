# Feature Spec

```text
OBJ: spec {{FEATURE}}.
AUTH: {{ROADMAP}} + {{PROJECT_SPECS}} + related specs/code/tests.
ASK first:
1 user behavior/success/failure
2 scope+/scope-/compat/migration
3 architecture/security/data/ops/acceptance
CREATE {{SPEC_DIR}}/{{FEATURE}}/:
- requirements.md = behavior/scope/interfaces/edges/decisions
- plan.md = numbered groups/deps/owners/migration/rollback
- validation.md = requirement->evidence/commands/merge gates/risks
CHECK: each requirement -> task + evidence; 3 files agree.
STOP: conflict / missing decision.
OUT: files; decisions; assumptions; open questions; implementation blocked pending approval.
NO IMPLEMENT before approval.
```
