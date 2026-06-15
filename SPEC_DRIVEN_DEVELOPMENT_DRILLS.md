# Spec-Driven Development With Coding Agents: Fluency Drills

Unofficial companion inspired by the
[DeepLearning.AI course materials](https://github.com/https-deeplearning-ai/sc-spec-driven-development-files/tree/main/prompts).  
Course lessons covered: 04-13  
Practice target: professional English plus spec-driven agent workflows

This guide contains original explanations, rewrites, and exercises. It does not
reproduce the upstream prompt files and is not affiliated with or endorsed by
DeepLearning.AI, JetBrains, or the course authors.

## How to Drill

For each lesson:

1. Read only the **Scenario**.
2. Speak or write your prompt without looking at the answer frame.
3. Compare your prompt with the **Production Frame**.
4. Complete the **Challenge**.
5. Record one phrase in your spaced-repetition system.

Do not memorize entire prompts. Memorize their architecture.

## Core Prompt Architecture

```text
Objective
-> Authoritative context
-> Required artifacts
-> Decisions or questions
-> Constraints
-> Validation
-> Completion and integration
```

Use this compact frame:

> **Objective:** [result]. **Read:** [authoritative files]. **Create or update:**
> [artifacts]. **Clarify:** [unresolved decisions]. **Constraints:** [boundaries].
> **Validate:** [checks]. **Complete when:** [observable final state].

---

## Lesson 04: Establish the Project Constitution

### Course Pattern

The agent reads stakeholder input, interviews the user, and creates:

- `specs/mission.md`
- `specs/tech-stack.md`
- `specs/roadmap.md`

Later prompts add server-side TypeScript, a framework decision, target audiences,
and SQLite.

### Vocabulary

- **constitution:** durable project-level principles and decisions
- **stakeholder input:** needs or constraints supplied by affected parties
- **target audience:** the people for whom the product is designed
- **technology rationale:** the reason a technology was selected
- **roadmap phase:** a small, ordered unit of planned delivery

### Recall Drill

Without looking above, answer:

1. Which three constitutional documents are created?
2. Which source contains stakeholder input?
3. Which decisions require user clarification?
4. Why should roadmap phases be small?

### Production Frame

> Read `README.md` as stakeholder input for AgentClinic. Before writing files,
> interview me about the mission, target audience, unresolved technology
> choices, and roadmap priorities. Then create `specs/mission.md`,
> `specs/tech-stack.md`, and `specs/roadmap.md`. Use server-side TypeScript and
> SQLite; recommend a framework with a concise rationale. Divide the roadmap
> into small, independently verifiable phases. Do not invent stakeholder
> decisions that I have not confirmed.

### Challenge

Add a validation section. Explain how you would determine whether the
constitution is coherent, complete, and internally consistent.

### English Upgrade

Weak:

> Use TypeScript and recommend framework.

Natural:

> Use server-side TypeScript and recommend a suitable framework, including the
> trade-offs that justify your recommendation.

---

## Lesson 05: Create a Feature Specification

### Course Pattern

The agent finds the next roadmap phase, creates a branch, interviews the user,
and writes a dated feature directory containing:

- `requirements.md`
- `plan.md`
- `validation.md`

The course then asks the agent to add a minimal home-page task group and keep all
feature documents synchronized.

### Vocabulary

- **feature scope:** behavior included in the feature
- **out of scope:** behavior intentionally excluded
- **task group:** a coherent group of implementation steps
- **acceptance criterion:** a condition required for accepting the feature
- **merge readiness:** the state in which the change is safe to integrate

### Recall Drill

Reconstruct the workflow in the correct order:

```text
write files / inspect roadmap / interview user / create branch /
identify next phase / validate consistency
```

### Production Frame

> Identify the next incomplete phase in `specs/roadmap.md` and create a feature
> branch. Read `specs/mission.md` and `specs/tech-stack.md`. Before writing the
> specification, interview me about requirements, implementation constraints,
> and acceptance criteria. Create
> `specs/YYYY-MM-DD-feature-name/requirements.md`, `plan.md`, and
> `validation.md`. Organize the plan into numbered task groups. Include a
> minimal AgentClinic home page and keep all three documents consistent.

### Challenge

Write five questions the agent should ask before drafting the specification.
Your questions must cover:

- user behavior;
- scope boundary;
- architecture constraint;
- failure behavior;
- acceptance evidence.

### English Upgrade

Instead of:

> Ask me about the feature spec.

Use:

> Interview me to resolve the feature's behavior, boundaries, technical
> constraints, and acceptance criteria before drafting the specification.

---

## Lesson 06: Implement From the Plan

### Course Pattern

The original prompt is intentionally short because the specification and plan
already hold the context.

### Principle

Short prompts are effective only when authoritative context is complete,
current, and unambiguous.

### Recall Drill

Explain the difference:

- **Prompt carries the context.**
- **Repository carries the context.**

### Production Frame

> Implement the remaining incomplete task groups in the active feature plan.
> Follow `requirements.md` and `validation.md`, update task status as work
> completes, run the specified checks after each coherent group, and stop if the
> implementation reveals a contradiction or missing decision in the spec.

### Challenge

List three conditions under which "Implement the remaining task groups" is
unsafe.

Expected themes:

- multiple active feature plans;
- stale or contradictory documents;
- no validation criteria;
- tasks with irreversible operations;
- unspecified ownership boundaries.

### English Upgrade

Useful phrase:

> Treat the specification as authoritative unless current repository evidence
> contradicts it; if that happens, stop and surface the discrepancy.

---

## Lesson 07: Keep Specifications and Code Synchronized

### Course Pattern

The lesson changes the component design, updates the feature specification,
marks the roadmap phase complete, and integrates the branch.

### Vocabulary

- **specification drift:** code and specifications no longer describe the same system
- **traceability:** ability to connect a requirement to implementation and tests
- **synchronize:** make related artifacts agree
- **integration:** incorporation of completed work into the main branch
- **branch cleanup:** deletion of a merged branch after verification

### Recall Drill

What must change when the layout is decomposed into header, main, and footer
components?

Name at least four artifacts or states.

### Production Frame

> Update the active feature plan and implementation so the layout is composed of
> separate header, main, and footer files. Add and correctly import the required
> stylesheet. Update the specification to record this component boundary. Run
> the validation checks, inspect the diff, mark the roadmap phase complete,
> commit the work, merge it into `main`, and delete the feature branch only
> after the merge is verified.

### Challenge

Find the dangerous assumption in this instruction:

> Mark the phase complete and merge the branch.

Answer:

> It assumes completion and merge readiness without requiring validation.

### English Upgrade

Prefer:

> Keep the implementation, feature plan, and roadmap status synchronized.

Avoid:

> Update everything accordingly.

---

## Lesson 08: Evolve Cross-Cutting Standards

### Course Pattern

The lesson introduces:

- Vitest and a package script;
- tests for existing behavior;
- responsive design across product and feature specs;
- a changelog convention;
- a reusable changelog skill;
- branch integration;
- roadmap consolidation.

### Vocabulary

- **cross-cutting concern:** requirement affecting multiple features or modules
- **retrofit:** add a capability to an existing system
- **propagate:** apply a decision across dependent artifacts
- **consolidate:** combine several units into one coherent unit
- **repository convention:** a rule consistently followed in the project

### Recall Drill

Classify each change:

| Change | Local or cross-cutting? |
|---|---|
| Add one home-page heading | |
| Adopt Vitest as the validation framework | |
| Require responsive web UI | |
| Fix one component typo | |
| Introduce a changelog workflow | |

### Production Frame

> Record Vitest and the package test command in the technology specification.
> Propagate that decision to affected feature specs and implementation. Add a
> representative test suite and run it. Record responsive design as a
> product-wide requirement, then update affected specifications and code. Create
> a reusable changelog workflow based on dated entries and repository history.
> Before merging, update the changelog, run validation, and verify that the
> consolidated roadmap still preserves scope and delivery order.

### Challenge

Describe the difference between:

- updating one feature specification;
- changing a project-wide standard;
- creating reusable workflow automation.

### English Upgrade

Use:

> Propagate this decision through every dependent specification and
> implementation artifact.

This is more precise than:

> Update all related things.

---

## Lesson 09: Refine, Review, and Document

### Course Pattern

The lesson adds brand colors, improves TypeScript props, reruns tests, delegates
review to multiple agents, and updates the changelog.

### Vocabulary

- **review perspective:** a defined lens used to inspect a change
- **type extraction:** moving a type from an inline declaration to a named definition
- **consistency review:** checking that related decisions agree
- **maintainability:** ease of understanding and safely changing software
- **changelog entry:** user- or maintainer-relevant record of completed work

### Recall Drill

Replace "review from three different perspectives" with three explicit roles.

Recommended roles:

1. correctness and requirements;
2. architecture and maintainability;
3. testing, accessibility, and user experience.

### Production Frame

> Apply the approved orange-and-black brand palette while preserving accessible
> contrast. Replace inline prop declarations with named TypeScript types where
> this improves reuse or readability, then rerun tests. Review the complete
> branch diff from three independent perspectives: requirements correctness,
> architecture and maintainability, and validation and user experience.
> Consolidate duplicate findings, fix material issues, rerun checks, and update
> the changelog with verified changes.

### Challenge

Explain why "see if anything could be better" produces weaker reviews than
explicit review lenses and severity criteria.

### English Upgrade

Use:

> Review the branch for requirement mismatches, behavioral regressions,
> maintainability risks, and missing validation.

Avoid:

> See whether anything looks wrong.

---

## Lesson 10: Integrate an MVP

### Course Pattern

The agent reviews the complete roadmap, creates an MVP branch and specification,
implements it, and then checks whether implementation exposed ambiguities.

### Vocabulary

- **minimum viable product (MVP):** smallest product that delivers the intended core value
- **integration plan:** ordered work needed to combine features
- **scope reconciliation:** resolving overlap, gaps, or conflicts between features
- **emergent requirement:** requirement discovered through implementation
- **specification feedback loop:** using implementation evidence to improve the spec

### Recall Drill

Answer in one sentence each:

1. Why is an MVP not simply "all unfinished roadmap items"?
2. Why must existing feature specs be reviewed together?
3. Why should the agent revisit the specs after implementation?

### Production Frame

> Review the roadmap and existing feature specifications to identify the
> smallest coherent MVP. Create an MVP branch and a specification directory with
> requirements, plan, and validation documents. Interview me about scope,
> integration decisions, and acceptance criteria before writing. Reconcile
> duplicated or conflicting feature requirements, implement the approved plan,
> run end-to-end validation, and report any ambiguity or missing decision that
> implementation exposed.

### Challenge

Create a two-column table:

| Candidate capability | Required for MVP? Why? |
|---|---|

Use evidence from mission, audience, and acceptance criteria rather than
personal preference.

### English Upgrade

Useful phrase:

> Implementation revealed a specification gap concerning [decision].

---

## Lesson 11: Reconstruct Specifications for Existing Work

### Course Pattern

The lesson creates a constitution for an existing project by reading
`README.md`, deriving roadmap input from `TODO.md`, interviewing the user, and
then implementing the plan.

### Vocabulary

- **brownfield project:** an existing system with code, history, and constraints
- **reverse specification:** documentation derived from an existing implementation
- **repository archaeology:** investigation of code and history to recover intent
- **authoritative source:** artifact responsible for defining a decision
- **reconciliation:** resolution of disagreement between sources

### Recall Drill

Rank these sources by authority for an existing project:

```text
current tests / README claims / TODO ideas / current code / user confirmation
```

There is no universal answer. Explain the authority of each source and how you
would resolve contradictions.

### Production Frame

> Reconstruct the AgentClinic constitution from current repository evidence.
> Read `README.md` for stakeholder intent, `TODO.md` for candidate roadmap work,
> and inspect the implementation for current behavior and technology choices.
> Interview me about the mission, target audience, technology gaps, and
> contradictions between sources. Create the three constitutional documents,
> clearly label inferred decisions, divide the roadmap into small phases, and
> implement only the approved plan.

### Challenge

Complete this sentence:

> `TODO.md` is evidence of ________, but it is not proof of ________.

Suggested answer:

> intended work; approved product scope

### English Upgrade

Use:

> The repository evidence conflicts with the documented intent.

---

## Lesson 12: Convert Repetition Into a Skill

### Course Pattern

A repeated feature-spec prompt becomes a local reusable skill. The agent then
uses that skill on the next roadmap feature.

### Vocabulary

- **workflow extraction:** converting repeated behavior into a reusable procedure
- **trigger condition:** situation in which a skill should be used
- **parameter:** value that varies between uses
- **invariant step:** step that remains the same in every use
- **progressive disclosure:** loading detailed guidance only when needed

### Recall Drill

Separate the feature-spec workflow into:

| Invariant | Variable |
|---|---|
| Read mission and technology specs | Feature name |
| Create requirements, plan, validation | |
| Interview before writing | |
| Use dated specification directory | |
| Find next roadmap phase | |

Fill the missing variable values.

### Production Frame

> Extract the repeated feature-specification workflow into a local skill. Define
> when it triggers, which repository files it reads, which questions it asks,
> which artifacts it creates, what it must never assume, and how completion is
> validated. Parameterize feature identity and roadmap phase while preserving
> the interview, specification, and validation sequence. Test the skill on the
> next roadmap feature and refine any ambiguous instruction.

### Challenge

Identify three failure modes of a reusable skill:

- it triggers too broadly;
- it assumes repository paths that do not exist;
- it hides critical decisions instead of asking;
- it creates artifacts without validation;
- it becomes stale when conventions change.

### English Upgrade

Use:

> Extract the stable workflow and parameterize the parts that vary.

---

## Lesson 13: Discover Test Gaps

### Course Pattern

The course ends with a broad question about which code needs more tests.

### Principle

A test-gap review should be risk-based, not driven only by line coverage.

### Vocabulary

- **untested path:** behavior no test currently exercises
- **critical path:** behavior essential to the product's core value
- **boundary condition:** input at or near an allowed limit
- **failure mode:** specific way a system can fail
- **risk-based testing:** prioritizing tests by likelihood and impact

### Recall Drill

Rank test candidates using:

```text
priority = impact x likelihood x change frequency x detection difficulty
```

### Production Frame

> Audit the repository for test gaps. Map critical user flows, business rules,
> state transitions, failure paths, integration boundaries, and recently
> changed code to existing tests. Rank missing coverage by production risk,
> explain the evidence for each finding, and propose the smallest high-value
> tests first. Do not use line coverage as the only prioritization signal.

### Challenge

Write one test-gap finding using:

> **Risk:** [failure]. **Evidence:** [untested behavior]. **Impact:** [effect].
> **Recommended test:** [specific scenario].

### English Upgrade

Instead of:

> What parts need more tests?

Use:

> Which untested behaviors create the greatest production risk, and what
> evidence supports that ranking?

---

## Mixed Retrieval Drills

## Drill A: Name the Missing Layer

For each prompt, identify the missing layer:

1. "Implement the feature."
2. "Update the spec."
3. "Review the code."
4. "Merge the branch."
5. "Add more tests."

Possible layers:

- authoritative context;
- scope;
- validation;
- review criteria;
- integration preconditions;
- risk priority.

## Drill B: Repair the Prompt

Rewrite each prompt in no more than 80 words:

1. "Use React."
2. "Make it responsive."
3. "Create an MVP."
4. "Ask me questions."
5. "Make a skill for this."

Each rewrite must include:

- the objective;
- one authoritative source;
- one constraint;
- one validation condition.

## Drill C: Specification Drift

Scenario:

> The code uses Vitest, `tech-stack.md` says Jest, the feature validation file
> says to run `npm test`, and `package.json` has no test script.

Respond as the agent. Your response must:

1. describe observed facts;
2. avoid inventing the intended framework;
3. ask one decision question;
4. propose a synchronization plan;
5. avoid editing until the contradiction is resolved.

## Drill D: Status Update

Give a 45-second update using:

> **Completed -> Evidence -> Discrepancy -> Decision needed -> Next step**

Scenario:

> You implemented two of four task groups. Tests pass. The third group requires
> a database choice missing from `tech-stack.md`.

## Drill E: Review Finding

Write a high-quality finding:

> The roadmap is marked complete, but one validation criterion has no test and
> responsive behavior was checked only at desktop width.

Use:

> **Severity -> Problem -> Evidence -> Impact -> Recommended action**

---

## Seven-Day Practice Schedule

| Day | Lessons | Output |
|---|---|---|
| 1 | 04-05 | Constitution prompt and feature-spec prompt |
| 2 | 06-07 | Implementation instruction and drift diagnosis |
| 3 | 08 | Cross-cutting change propagation plan |
| 4 | 09 | Three-lens review request and one finding |
| 5 | 10-11 | MVP integration and brownfield reconstruction |
| 6 | 12-13 | Skill extraction and risk-based test audit |
| 7 | Mixed drills | One complete spec-driven workflow from memory |

## Scoring Rubric

Score each category from 0 to 2.

| Category | 0 | 1 | 2 |
|---|---|---|---|
| Objective | absent | implied | explicit and observable |
| Context | absent | partial | authoritative sources named |
| Artifacts | vague | incomplete | paths and purpose defined |
| Clarification | none | generic | decisions grouped precisely |
| Constraints | absent | broad | concrete boundaries |
| Validation | absent | "run tests" | behavior and checks specified |
| Completion | "done" | partial | integration state defined |
| English | ambiguous | understandable | concise and professional |

Target:

- **0-7:** reconstruct the core frame.
- **8-11:** strengthen constraints and validation.
- **12-14:** production-capable prompt.
- **15-16:** precise, reusable agent instruction.

## Final Recall

Complete from memory:

> A specification-driven prompt names the ________, points to the
> ________ context, defines required ________, resolves missing ________,
> states operational ________, and provides observable ________ criteria.

Answer:

> objective; authoritative; artifacts; decisions; constraints; validation

## Final Rule

The prompt should not carry every detail. It should direct the agent to the
right authoritative artifacts, expose unresolved decisions, and define how
success will be verified.
