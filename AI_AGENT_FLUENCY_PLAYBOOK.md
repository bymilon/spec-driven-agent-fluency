# AI Coding Agent Fluency Playbook

Version: 2026-06-15  
Audience: non-native English-speaking engineering interns  
Target: clear B2-to-C1 workplace communication with coding agents and engineering teams

## How This Playbook Was Built

The initial drafting process studied a private set of third-party visual
references. Those images are not distributed with the public repository. The
references shared this effective teaching pattern:

1. Name one domain.
2. Divide it into a small set of concepts.
3. Define each concept in plain language.
4. Explain why it matters.
5. Show a process or checklist.
6. End with one memorable rule.

This playbook applies that pattern to AI-assisted software development. It does
not reproduce the reference images or treat their simplified claims as
authoritative.

## Your Communication Upgrade

Your intended request:

> Reverse-engineer the images in `resources/` and use their teaching structure
> to build my fluency in AI coding-agent conversations and developer workflows.

Natural team introduction:

> I have just joined the team as an intern. English is not my first language.
> I want to become fluent in the language, workflows, and engineering practices
> used by teams that work with AI coding agents.

Key corrections:

- Say **"I have just joined the team"**, not "I am just onboard."
- Say **"English is not my first language"**, not "I am non-native English."
- Spell **conversation**, **vocabulary**, and **understand**.
- Use **onboard** as a verb: "Please onboard me." Use **onboarding** as a noun:
  "My onboarding starts today."

## The Mentor Contract

For future work, use this response pattern:

1. **Task first:** solve the engineering problem.
2. **English upgrade:** correct no more than three high-impact issues.
3. **Native rewrite:** provide one concise version a senior engineer would use.
4. **Vocabulary:** teach one reusable term in context.
5. **Recall:** occasionally ask you to reuse a phrase without looking it up.

Corrections should improve precision without interrupting urgent engineering
work.

---

## 01. AI Coding Agent Essentials

### The Core Model

An effective request contains four parts:

| Part | Question | Example |
|---|---|---|
| Goal | What must change? | Add rate limiting to the login endpoint. |
| Context | What should the agent inspect? | Start with `src/auth/` and the existing middleware. |
| Constraints | What must remain true? | Keep the public API stable. Add no dependencies. |
| Done when | How will we verify completion? | Unit tests and lint pass; excess requests return HTTP 429. |

### Default Sentence Frame

> **Goal:** [desired result]. **Context:** inspect [files, errors, examples].
> **Constraints:** preserve [behavior or boundary]. **Done when:** [observable
> checks pass].

Weak:

> Fix login.

Production-grade:

> Users are logged out when access tokens expire, even when the refresh token is
> valid. Reproduce the failure in `src/auth/`, add a regression test, and make
> the smallest fix that preserves the current API. The task is complete when the
> focused tests and the full authentication suite pass.

### Why It Matters

Clear completion criteria reduce assumptions and make the result easier to test
and review.

### Drill

Rewrite this request with all four parts:

> Make the dashboard faster.

---

## 02. Conversation Basics

### Ten High-Value Speech Acts

| Intent | Natural phrase |
|---|---|
| Direct | "Start by inspecting the existing implementation." |
| Scope | "Limit this change to the authentication module." |
| Clarify | "What assumption are you making about token lifetime?" |
| Confirm | "Confirm your understanding before editing files." |
| Challenge | "What evidence supports that conclusion?" |
| Compare | "Compare both approaches against our constraints." |
| Correct | "That changes public behavior; keep the API stable." |
| Verify | "Run the focused test, then the full suite." |
| Summarize | "Summarize the root cause, patch, and residual risk." |
| Stop | "Pause implementation. We need to resolve the data model first." |

### Precision Vocabulary

- **assumption:** something treated as true without sufficient evidence
- **constraint:** a boundary the solution must respect
- **invariant:** a condition that must always remain true
- **acceptance criterion:** an observable condition for accepting the work
- **trade-off:** a gain that requires accepting a cost
- **residual risk:** risk that remains after mitigation

### Better Than "I Think"

Choose the phrase that matches your evidence:

- "I suspect..." for an unverified hypothesis.
- "The logs suggest..." for partial evidence.
- "The test confirms..." for reproduced evidence.
- "The code guarantees..." only when an invariant is enforced.
- "I am not yet certain..." when uncertainty matters.

### Drill

Replace "I think the database is broken" with three versions: hypothesis,
evidence-based observation, and confirmed finding.

---

## 03. Planning and Prototyping

### Use Planning When

- the task crosses module boundaries;
- requirements are ambiguous;
- rollback is difficult;
- security or data integrity is involved;
- you cannot describe the expected diff in one sentence.

For a small, obvious change, planning can add unnecessary overhead.

### Planning Vocabulary

| Term | Meaning |
|---|---|
| decompose | divide a large task into smaller tasks |
| dependency | work that must happen before other work |
| milestone | a verifiable intermediate result |
| blast radius | the scope of possible impact |
| rollback | restoration of the previous safe state |
| migration | controlled movement from one state or system to another |
| spike | time-boxed investigation used to reduce uncertainty |

### Planning Request

> Explore the current request flow before proposing changes. Then produce a
> plan with affected files, dependencies, risks, test strategy, migration
> order, and rollback steps. Do not implement until the plan is coherent.

### Plan Review Questions

1. What user-visible behavior changes?
2. Which interfaces or schemas change?
3. What can fail halfway through?
4. How will we detect failure?
5. How will we recover?
6. Which tests prove the change?

### Drill

Explain why this phrase is stronger than "Make a plan":

> Separate discovery from implementation and identify unresolved decisions.

---

## 04. Workflow Mapping

### Ten Maps for Agentic Engineering

| Map | Use it to understand |
|---|---|
| Request flow | how data moves through modules |
| Dependency graph | what imports, calls, or depends on what |
| State machine | valid states and transitions |
| Data lineage | where data originates, changes, and persists |
| Failure path | how errors propagate and recover |
| Permission boundary | who or what may perform an action |
| Deployment path | how code reaches production |
| Test pyramid | where confidence comes from |
| Ownership map | which team owns each component |
| Agent handoff map | what context passes between agents or people |

### Mapping Verbs

Use **trace**, **locate**, **identify**, **enumerate**, **classify**, **connect**,
**sequence**, **differentiate**, **validate**, and **document**.

### Example Request

> Trace the request from the HTTP handler to persistence. Identify validation,
> authorization, transformation, and error-handling boundaries. Return a
> numbered flow with file paths and flag any behavior you could not verify.

### Why It Matters

Mapping converts an unfamiliar repository into a shared mental model. A shared
model improves both technical decisions and technical English.

---

## 05. Research and Strategy

### Evidence Order

Use evidence in this order:

1. current code and tests;
2. repository documentation and architecture decisions;
3. schemas, generated specifications, and runbooks;
4. official vendor documentation;
5. primary standards and research;
6. secondary commentary only when necessary.

### Research Vocabulary

- **authoritative:** officially responsible for defining the fact
- **primary source:** original specification, paper, code, or data
- **corroborate:** confirm using independent evidence
- **triangulate:** compare several evidence sources
- **provenance:** where information came from
- **stale:** no longer current
- **inference:** a conclusion derived from evidence, not directly observed

### Research Request

> Verify this against the current implementation and first-party documentation.
> Separate observed facts from inference. Cite the exact files or sources, and
> state what remains uncertain.

### Useful Distinctions

- **Symptom:** what was observed.
- **Cause:** the mechanism that produced the symptom.
- **Contributing factor:** something that increased likelihood or impact.
- **Root cause:** the underlying condition whose correction prevents recurrence.

### Drill

Turn "The cache caused it" into a statement that distinguishes observation,
hypothesis, and proof.

---

## 06. Agent Tool Ecosystem

### Tool Categories

| Category | Purpose |
|---|---|
| repository search | locate files, symbols, patterns, and history |
| shell | inspect state and run deterministic commands |
| patching | make reviewable, scoped edits |
| tests and linters | verify behavior and conventions |
| browser tools | inspect rendered behavior and accessibility |
| documentation retrieval | use current authoritative guidance |
| MCP/connectors | reach governed external systems |
| skills/instructions | encode reusable domain workflows |
| hooks | enforce deterministic actions |
| worktrees/sandboxes | isolate parallel or risky work |

### Tool Selection Language

> Use the narrowest tool that can produce reliable evidence.

> Read before editing. Reproduce before fixing. Verify after changing.

> Do not run destructive commands without explicit approval and a recovery plan.

### Important Distinction

- **Instruction:** advisory guidance the agent interprets.
- **Hook or policy:** deterministic enforcement performed by the system.

Do not rely on prose instructions when a critical rule can be enforced by CI,
permissions, schemas, or hooks.

---

## 07. Testing and Validation

### Validation Ladder

1. Reproduce the current behavior.
2. Write or identify a failing focused test.
3. Implement the smallest coherent change.
4. Run the focused test.
5. Run related integration checks.
6. Run the broader suite, lint, and static analysis.
7. Inspect the diff.
8. Report checks that were not run.

### Testing Vocabulary

| Term | Meaning |
|---|---|
| regression | previously working behavior that now fails |
| reproduction | reliable steps that trigger a defect |
| fixture | controlled test data or setup |
| assertion | a condition the test requires to be true |
| false positive | a check reports a problem that is not real |
| false negative | a check misses a real problem |
| flaky test | a test with inconsistent results under the same conditions |
| coverage gap | important behavior that no test exercises |

### Verification Request

> Reproduce the issue before changing code. Add a regression test that fails for
> the correct reason, implement the fix, run the focused and related suites, and
> report any checks you could not run.

### Never Say

> It should work.

Say:

> The focused test and authentication suite pass. I did not run the end-to-end
> suite because the required service is unavailable.

---

## 08. Review and Feedback

### Review Order

1. correctness;
2. security and data integrity;
3. behavioral regressions;
4. architecture and maintainability;
5. tests and observability;
6. clarity and style.

### Severity Language

- **Blocker:** unsafe to merge.
- **High:** likely production failure, security issue, or data loss.
- **Medium:** meaningful defect or maintainability risk.
- **Low:** limited impact or local improvement.
- **Nit:** optional polish; never disguise a requirement as a nit.

### Finding Structure

> **[Severity] Problem:** [specific defect].  
> **Evidence:** [file, line, behavior, or test].  
> **Impact:** [what can fail and for whom].  
> **Recommended change:** [concrete correction].

### Respectful Disagreement

- "I disagree because this violates the stated invariant."
- "I may be missing context. What requires this additional abstraction?"
- "This solves the immediate case but leaves the concurrent path unsafe."
- "The trade-off is reasonable, but it should be explicit in the ADR."
- "Can we prove that assumption with a test or trace?"

### Drill

Rewrite "This code is bad" as an evidence-based review finding.

---

## 09. Agent Collaboration Principles

### Ten Principles

1. **Evidence before confidence.**
2. **Context before execution.**
3. **Small coherent changes before broad rewrites.**
4. **Explicit constraints before autonomy.**
5. **Verification before completion claims.**
6. **Repository conventions before personal preference.**
7. **Parallelize independent work; isolate overlapping work.**
8. **Escalate irreversible actions.**
9. **Record durable decisions in authoritative artifacts.**
10. **Keep humans accountable for acceptance.**

### Multi-Agent Delegation Frame

> Delegate [bounded task] to [agent/role]. Provide [required context]. The agent
> may change [owned files] but must not change [protected boundary]. Expected
> output: [artifact]. Acceptance: [checks]. Report blockers and uncertainty.

### Handoff Vocabulary

- **owner:** accountable person or team
- **scope boundary:** work included and excluded
- **deliverable:** artifact the task must produce
- **handoff:** transfer of work and context
- **synchronization point:** moment parallel work must be reconciled
- **conflict:** incompatible edits, requirements, or assumptions

### Parallel Work Rule

Never assign two agents to modify the same files unless you have an explicit
merge strategy.

---

## 10. AI-Native Development Workflow

### The Production Loop

```text
Frame -> Explore -> Plan -> Implement -> Verify -> Review -> Integrate -> Learn
```

### Status Update Formula

> **Completed:** [verified result].  
> **In progress:** [current action].  
> **Blocked by:** [specific dependency or decision].  
> **Next:** [immediate step].  
> **Risk:** [only if material].

### Blocker Language

Weak:

> It doesn't work.

Strong:

> The integration test cannot start because port 5432 is already occupied. I
> confirmed the application code has not run. I need either permission to stop
> the existing process or a test configuration that uses another port.

### Completion Language

Use:

- "Implemented and verified..."
- "Partially implemented; the remaining blocker is..."
- "The code is complete, but production readiness is not yet established..."
- "No code change was needed; the issue was configuration..."

Avoid:

- "Done" without evidence.
- "Perfect" for unverified work.
- "Production-ready" without operational, security, and rollback checks.

---

## 11. Inclusive Professional English

### Plain Language Rules

1. Put the main point first.
2. Prefer active voice when the actor matters.
3. Use one term consistently for one concept.
4. Replace vague pronouns with explicit nouns.
5. Keep one main idea per sentence.
6. Use numbered lists for sequence and bullets for unordered items.
7. Define uncommon acronyms on first use.
8. Avoid idioms when working across cultures.

### Ambiguous vs Precise

| Ambiguous | Precise |
|---|---|
| "Fix it there." | "Update token validation in `src/auth/token.ts`." |
| "Use the normal approach." | "Follow the retry pattern in `queue/worker.ts`." |
| "Make it robust." | "Handle timeout, cancellation, and duplicate delivery." |
| "Test everything." | "Run unit, integration, lint, and type checks." |
| "ASAP." | "Please provide the reviewed patch by 15:00 UTC." |

### Repair Phrases

Use these when communication fails:

- "Let me restate the requirement more precisely."
- "I used the wrong term. I meant..."
- "We may be using different definitions of..."
- "Please separate what you observed from what you inferred."
- "Before we continue, confirm the expected behavior for..."
- "I understand the implementation, but not the reason for the constraint."

### CEFR-Aligned Target

Aim first for strong B2 workplace performance:

- explain a technical position and its advantages and disadvantages;
- participate actively in collaborative problem-solving;
- clarify misunderstandings;
- relay detailed instructions accurately;
- write clear, structured technical messages.

Then develop C1 behaviors:

- coordinate complex collaborative work;
- revise instructions as constraints change;
- negotiate trade-offs precisely;
- adapt tone to engineers, product managers, and executives;
- reformulate complex ideas without losing meaning.

---

## Core Vocabulary: The First 40 Words

Learn these as phrases, not isolated definitions.

| Domain | Terms |
|---|---|
| Scope | goal, context, constraint, boundary, criterion |
| Reasoning | assumption, evidence, inference, hypothesis, rationale |
| Change | patch, refactor, migration, rollback, compatibility |
| Quality | invariant, regression, edge case, failure mode, coverage |
| Workflow | dependency, milestone, blocker, handoff, ownership |
| Review | finding, severity, impact, trade-off, residual risk |
| Operations | deploy, monitor, mitigate, recover, escalate |
| Agents | prompt, context window, tool call, sandbox, instruction |

### Collocations to Memorize

Native fluency depends on common word combinations:

- **meet a requirement**
- **satisfy a constraint**
- **preserve an invariant**
- **reproduce a defect**
- **isolate a failure**
- **mitigate a risk**
- **surface a blocker**
- **resolve an ambiguity**
- **validate an assumption**
- **narrow the scope**
- **inspect the diff**
- **run the suite**
- **open a pull request**
- **request approval**
- **hand off the task**

---

## Daily Fluency Loop: 20 Minutes

This routine uses retrieval, spaced practice, and realistic task production.

### Minutes 0-3: Recall

Without looking at the playbook, write:

- the four parts of an agent request;
- five workflow verbs;
- one phrase for uncertainty;
- one phrase for disagreement.

### Minutes 3-8: Rewrite

Take one vague request from your actual work and rewrite it with goal, context,
constraints, and done-when conditions.

### Minutes 8-13: Simulate

Speak a 60-second status update aloud. Record it if possible. Use:

> completed -> evidence -> blocker -> next step

### Minutes 13-17: Respond

Answer one realistic agent message. Clarify an assumption, correct scope, or
request verification.

### Minutes 17-20: Compress

Summarize the task in:

1. one paragraph;
2. three bullets;
3. one sentence.

Compression develops control over detail and audience.

### Spacing Schedule

Review new phrases after approximately:

- 1 day;
- 3 days;
- 7 days;
- 14 days;
- 30 days.

Do not merely reread. Retrieve the phrase, use it in a new engineering context,
then check accuracy.

---

## Weekly Assessment

Score each item from 0 to 2:

- **0:** absent or unclear
- **1:** present but imprecise
- **2:** precise and natural

| Skill | Score |
|---|---:|
| States the goal first | /2 |
| Supplies relevant context | /2 |
| Defines constraints | /2 |
| Defines "done" with evidence | /2 |
| Distinguishes fact from inference | /2 |
| Uses specific engineering verbs | /2 |
| Reports blockers precisely | /2 |
| Gives respectful, evidence-based feedback | /2 |
| Summarizes without losing key meaning | /2 |
| Uses consistent terminology | /2 |

Interpretation:

- **0-8:** build sentence control and core vocabulary.
- **9-14:** functional; improve precision and verification language.
- **15-17:** strong independent collaborator.
- **18-20:** advanced professional fluency.

---

## Ready-to-Use Templates

### Feature

> Implement [feature] for [user/scenario]. Start by inspecting [files/patterns].
> Preserve [interfaces/invariants]. Do not [excluded changes]. Add [tests].
> Complete the task when [observable behavior and checks].

### Bug

> Symptom: [observed behavior]. Reproduction: [steps]. Expected: [behavior].
> Suspected area: [files/module], but verify the cause. Add a regression test,
> make the smallest coherent fix, and run [checks].

### Investigation

> Investigate [question] without editing files. Trace [flow], cite [evidence],
> separate observations from inference, and return [format]. Flag uncertainty.

### Refactor

> Refactor [component] to improve [quality]. Preserve public behavior and APIs.
> First map dependencies and propose milestones. Include migration, testing, and
> rollback strategies. Implement only after the plan is reviewed.

### Review

> Review this change for correctness, security, regressions, and missing tests.
> Lead with findings ordered by severity. Cite file locations, explain impact,
> and recommend concrete fixes. Do not spend time on cosmetic preferences unless
> they affect maintainability or standards.

### Status

> Completed: [result and evidence]. In progress: [work]. Blocked by: [specific
> issue]. Next: [action]. Risk: [material risk or "none identified"].

---

## Source Standard

Primary guidance used for this playbook, checked on 2026-06-15:

- [OpenAI Codex: Best practices](https://developers.openai.com/codex/learn/best-practices)
- [OpenAI Codex: Prompting](https://developers.openai.com/codex/prompting)
- [OpenAI Codex: Workflows](https://developers.openai.com/codex/workflows)
- [OpenAI Codex: Custom instructions with AGENTS.md](https://developers.openai.com/codex/guides/agents-md)
- [GitHub: Repository custom instructions for Copilot](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions)
- [Anthropic: Claude Code best practices](https://code.claude.com/docs/en/best-practices)
- [Council of Europe: CEFR Companion Volume](https://rm.coe.int/common-european-framework-of-reference-for-languages-learning-teaching/16809ea0d4)
- [Google: Technical Writing One](https://developers.google.com/tech-writing/one)
- [Digital.gov: Plain language guide](https://digital.gov/guides/plain-language)
- [NIST SP 800-218: Secure Software Development Framework](https://csrc.nist.gov/pubs/sp/800/218/final)
- [NIST SP 800-218A: Generative AI SSDF Community Profile](https://csrc.nist.gov/pubs/sp/800/218/a/final)

Learning method references:

- Roediger, H. L., and Karpicke, J. D. (2006), "Test-Enhanced Learning:
  Taking Memory Tests Improves Long-Term Retention."
- Cepeda, N. J. et al. (2006), "Distributed Practice in Verbal Recall Tasks:
  A Review and Quantitative Synthesis."

## Final Rule

Fluent engineers do not use the most complicated English. They make scope,
evidence, decisions, uncertainty, and completion easy for other people and
agents to understand.
