# MVP Integration

## Use When

Reconciling several feature specifications into the smallest coherent product
that can deliver and validate core value.

## Required Inputs

- `{{MISSION_FILE}}`
- `{{ROADMAP_FILE}}`
- `{{FEATURE_SPECS}}`
- `{{MVP_SPEC_DIRECTORY}}`

## Prompt

```text
Define and prepare the minimum viable product.

Read:
- {{MISSION_FILE}};
- {{ROADMAP_FILE}};
- {{FEATURE_SPECS}};
- project technology and operational specifications;
- current implementation and validation evidence.

Identify the smallest coherent capability set that:
1. delivers the mission's core user outcome;
2. is safe, operable, and testable;
3. includes dependencies required by essential capabilities;
4. enables validation of the most important product assumptions.

Before writing, interview me about scope, exclusions, integration conflicts,
operational constraints, release criteria, and acceptable residual risk.

Create under {{MVP_SPEC_DIRECTORY}}:
- `requirements.md` for included capabilities, exclusions, reconciled decisions,
  known limitations, and assumptions;
- `plan.md` for ordered integration work, dependencies, migrations, deployment,
  and rollback preparation;
- `validation.md` for end-to-end functional, security, accessibility,
  performance, and operational evidence.

Do not include a capability merely because it already appears on the roadmap.
Do not silently resolve conflicting feature assumptions in code.

After implementation, report specification gaps and emergent requirements with
their evidence. Update approved specifications before changing product behavior.
```

## Quality Gate

An MVP minimizes scope, not quality controls required for safe learning and
operation.

