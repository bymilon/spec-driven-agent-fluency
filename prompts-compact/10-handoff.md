# Handoff

```text
OBJ: {{OBJECTIVE}}
AUTH: {{AUTHORITATIVE_FILES}}
DONE: {{COMPLETED}}
EVIDENCE: {{EVIDENCE}}
NOW: {{CURRENT_STATE}}
BLOCKED/DECISION: {{BLOCKERS}}
NEXT: {{NEXT}}
RISK: {{RISKS}}
CONTEXT: auth files; branch/commit; worktree state; verified assumptions; approvals needed; checks not-run + why.
LABEL: complete/partial/blocked/unverified.
STOP: evidence missing -> label unverified; decision missing -> label blocked.
VERIFY: status matches repo/spec/test evidence.
NO: "done"/"production-ready"/"should work" without evidence.
OUT: concise; continuation-ready; no repeated discovery needed.
```
