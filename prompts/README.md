# Prompt Library

Reusable templates for spec-driven work with coding agents.

These prompts are starting contracts, not magic commands. Replace every
`{{PLACEHOLDER}}`, remove irrelevant sections, and align validation with the
repository's actual tooling and risk.

## Prompt Index

| Prompt | Use it for |
| --- | --- |
| [Task Contract](00-task-contract.md) | Framing a bounded engineering task |
| [Project Constitution](01-project-constitution.md) | Establishing project-level direction |
| [Feature Specification](02-feature-specification.md) | Turning roadmap work into an approved spec |
| [Plan Implementation](03-plan-implementation.md) | Executing approved task groups |
| [Specification Synchronization](04-specification-synchronization.md) | Keeping specs, code, tests, and roadmap aligned |
| [Cross-Cutting Change](05-cross-cutting-change.md) | Changing project-wide standards or tooling |
| [Multi-Perspective Review](06-multi-perspective-review.md) | Reviewing a branch through explicit risk lenses |
| [MVP Integration](07-mvp-integration.md) | Reconciling features into a coherent MVP |
| [Brownfield Reconstruction](08-brownfield-reconstruction.md) | Recovering intent from an existing repository |
| [Test-Gap Audit](09-test-gap-audit.md) | Prioritizing missing tests by production risk |
| [Status and Handoff](10-status-and-handoff.md) | Reporting progress, blockers, and residual risk |

## Core Architecture

Each strong prompt should define:

```text
Objective
-> Authoritative context
-> Required artifacts
-> Decisions to clarify
-> Scope and constraints
-> Validation
-> Completion evidence
```

## Usage Rules

1. Point the agent to authoritative repository files.
2. State what is in scope and explicitly out of scope.
3. Require clarification for decisions the agent should not invent.
4. Define observable acceptance criteria.
5. Include stop conditions for ambiguity, risk, or contradiction.
6. Require the agent to report checks it could not run.
7. Keep consequential approvals with accountable humans.

## Placeholder Convention

- `{{UPPER_SNAKE_CASE}}` means required user input.
- `[optional text]` means a section that may be removed.
- File paths should be repository-relative whenever possible.

## Quality Check

Before using a prompt, ask:

- Can the agent identify the exact desired outcome?
- Does it know which evidence is authoritative?
- Are important assumptions exposed?
- Are destructive or irreversible operations gated?
- Can a reviewer determine whether the task is complete?

