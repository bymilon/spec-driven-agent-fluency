# Brownfield Reconstruction

## Use When

An existing repository lacks reliable specifications or contains conflicting
documentation, code, tests, and backlog items.

## Required Inputs

- `{{STAKEHOLDER_DOCUMENTS}}`
- `{{BACKLOG_SOURCES}}`
- `{{OUTPUT_SPEC_DIRECTORY}}`

## Prompt

```text
Reconstruct the project specification from current repository evidence.

Inspect:
- stakeholder documents: {{STAKEHOLDER_DOCUMENTS}};
- candidate backlog sources: {{BACKLOG_SOURCES}};
- source code, tests, configuration, schemas, dependencies, and CI;
- relevant Git history and architecture decisions;
- operational and security documentation.

Classify material statements as:
- observed: confirmed by current repository evidence;
- documented: stated by an authoritative artifact;
- inferred: concluded from incomplete evidence;
- proposed: suggested but not approved;
- approved: confirmed by an accountable stakeholder.

Identify contradictions between intent, implementation, tests, and planned work.
Interview me about mission, audiences, current priorities, technology gaps, and
each material contradiction.

Create under {{OUTPUT_SPEC_DIRECTORY}}:
- `mission.md`;
- `tech-stack.md`;
- `roadmap.md`.

Preserve provenance for consequential claims. Treat backlog entries as proposed
work, not approved product scope. Treat current code as implemented behavior,
not automatic proof of intended behavior.

Do not implement inferred requirements. Report unresolved contradictions and
the decisions needed to proceed.
```

## Quality Gate

Reverse specification must expose uncertainty instead of converting guesses
into authoritative documentation.

