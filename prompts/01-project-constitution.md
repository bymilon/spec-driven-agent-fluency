# Project Constitution

## Use When

Starting a project or formalizing direction for a repository whose mission,
technology decisions, and delivery order are not yet explicit.

## Required Inputs

- `{{STAKEHOLDER_SOURCES}}`
- `{{KNOWN_CONSTRAINTS}}`
- `{{SPEC_DIRECTORY}}`

## Prompt

```text
Establish a project constitution for this repository.

Evidence gathering

Read {{STAKEHOLDER_SOURCES}} and inspect the current repository structure,
configuration, dependencies, tests, and documentation. Treat current code as
evidence of implementation, not automatic proof of intended product behavior.

Interview

Before writing constitutional files, ask grouped questions about:
1. mission, user problem, target audiences, and explicit non-goals;
2. technology constraints, deployment environment, security, data, and
   operational requirements;
3. roadmap priorities, dependencies, release boundaries, and acceptance.

Challenge assumptions and identify contradictions between stakeholder input and
repository evidence. Do not invent unresolved product or architecture choices.

Artifacts

Create under {{SPEC_DIRECTORY}}:
- `mission.md`: problem, users, outcomes, principles, and non-goals;
- `tech-stack.md`: approved technologies, constraints, rationale, and
  unresolved decisions;
- `roadmap.md`: small ordered phases with dependencies and observable exit
  criteria.

Known constraints

{{KNOWN_CONSTRAINTS}}

Validation

Before completion:
- check that the three documents do not contradict each other;
- confirm every roadmap phase supports the mission;
- confirm technology choices support roadmap requirements;
- label observed, inferred, proposed, and approved decisions;
- list unresolved questions requiring stakeholder approval.

Do not implement roadmap work until the constitution is reviewed.
```

## Quality Gate

Technology names without rationale, roadmap phases without exit criteria, and
audiences without concrete needs are incomplete.

