# Compact Prompt Library

Token-lean agent prompts. Telegraph style: nouns + verbs; low connective prose.

Use for agent input, not human-facing documentation or professional English
practice. Prefer full [`prompts/`](../prompts/README.md) when ambiguity, risk, or
team communication matters more than token cost.

## Syntax

```text
OBJ = objective
AUTH = authoritative context
SCOPE = included/excluded work
DO = actions
STOP = escalation conditions
VERIFY = checks
OUT = completion report
```

Symbols:

- `->` sequence
- `+` required combination
- `/` alternatives
- `;` separate constraints
- `!=` must differ
- `?` unresolved decision

## Files

| Prompt | Purpose |
| --- | --- |
| [Task](00-task.md) | General bounded task |
| [Constitution](01-constitution.md) | Project direction |
| [Feature Spec](02-feature-spec.md) | Requirements + plan + validation |
| [Implement](03-implement.md) | Execute approved plan |
| [Sync](04-sync.md) | Align specs + code + tests |
| [Standard](05-standard.md) | Cross-cutting change |
| [Review](06-review.md) | Multi-lens review |
| [MVP](07-mvp.md) | Minimum coherent product |
| [Brownfield](08-brownfield.md) | Recover existing intent |
| [Test Audit](09-test-audit.md) | Rank coverage gaps |
| [Handoff](10-handoff.md) | Status + continuation context |

## Compression Rule

Delete politeness, repetition, explanation. Keep nouns, verbs, paths, gates,
evidence. Never compress away approvals, safety boundaries, or validation.

Current 11-template set uses about 66% fewer whitespace-delimited words and 60%
fewer characters than the full library. Actual token savings vary by model and
tokenizer.
