# AI Skills For Life Deep Module Map

## Purpose

This map defines durable module boundaries for AI Skills For Life: a public repository of reusable AI skills for everyday, non-technical decisions.

Because the product is currently a skill repository rather than a conventional application, these modules are best understood as **skill-system responsibilities**. They describe the stable abstractions future skills, docs, examples, and tooling should rely on without forcing a specific folder structure, runtime architecture, service split, or framework.

A module in this map is valid only when it gives the rest of the repo a simple capability while hiding meaningful workflow, policy, quality, or orchestration complexity.

## Current Product Shape

AI Skills For Life is centered on skills that users can run in an AI agent environment. Users may:

- install skills through agentskills.io when they prefer that path
- clone this repository and run Codex, Gemini, Claude, Windsurf, or a similar agent from the repo root
- choose a skill by life situation rather than by technical category

The primary author and maintainer creates the skills. Public contributions may happen later, but the initial design center is not community authoring. Users consume the skills; they are not expected to understand how a skill is internally prompted, sequenced, researched, or formatted.

## Deep Modules

### 1. Life Skill Experience

**Suggested slug:** `life-skill-experience`

**Simple interface / outside promise:** Let a user invoke a skill for a real-life situation and be guided from messy context to a useful outcome.

**Hidden complexity:**

- translating a broad life situation into a focused workflow
- deciding what context must be collected before analysis
- sequencing questions one at a time
- keeping the tone practical, warm, and non-corporate
- deciding when to proceed, when to ask more, and when to state assumptions
- coordinating research, analysis, safety caveats, and artifact creation inside a skill

**Owns:**

- the end-to-end user experience inside an individual skill
- skill-specific interview flow
- skill-specific decision path and analysis approach
- skill-specific output artifact requirements
- the practical “nice dude helping you think” feel of a skill interaction

**Does not own:**

- global quality standards every skill must follow
- shared research freshness rules
- repository-level discovery or installation guidance
- specific implementation technology or CLI runtime behavior

**Key scenarios:**

- A user says, “Help me analyze whether this shop idea is worth exploring.”
- A user asks for help comparing expensive products before buying.
- A user wants to plan a trip and needs the skill to structure research and tradeoffs.
- A user needs help organizing a household or family decision.

**Related modules:**

- Uses `skill-quality-system` for shared expectations.
- Uses `research-freshness-system` when current facts matter.
- Produces through `artifact-system`.
- Is surfaced by `skill-discovery-and-access`.

**Boundary notes:**

This is not one module per life domain. Small business, travel, home planning, and consumer research are product domains where skills may exist. The deep module is the reusable experience shape that hides the complexity of turning vague life goals into guided AI workflows.

---

### 2. Skill Quality System

**Suggested slug:** `skill-quality-system`

**Simple interface / outside promise:** Define what makes a skill good enough to belong in AI Skills For Life.

**Hidden complexity:**

- maintaining consistency across independently written skills
- preventing skills from becoming generic prompt snippets
- defining required skill ingredients without forcing identical outputs
- keeping skills guided but not controlling
- balancing practicality, safety, warmth, and user ownership
- deciding which expectations belong repo-wide versus inside a specific skill

**Owns:**

- shared standards for skill purpose, trigger conditions, interview posture, and final behavior
- rules that every skill should make assumptions explicit
- expectations for practical outputs and next actions
- quality checks that prevent vague, motivational, or overly generic skills
- repo-level guidance for what a skill must not claim or become

**Does not own:**

- the exact interview questions for each skill
- the exact artifact template for each skill
- real-time research policies, except by requiring skills to follow them
- public contribution process as a primary design concern

**Key scenarios:**

- The maintainer adds a new consumer research skill and needs to know what standards it must satisfy.
- A future skill draft sounds like a generic ChatGPT prompt and needs to be tightened into a repeatable workflow.
- Two skills use different formats, but both need to remain recognizable as AI Skills For Life skills.

**Related modules:**

- Constrains `life-skill-experience`.
- Sets expectations for `artifact-system`.
- Requires `research-freshness-system` when current information matters.
- Provides language that `skill-discovery-and-access` can explain to users.

**Boundary notes:**

This module is a shared standard, not a contribution program. It can support PR review later, but its primary job is helping the maintainer create coherent skills over time.

---

### 3. Research Freshness System

**Suggested slug:** `research-freshness-system`

**Simple interface / outside promise:** Decide when a skill must use current information and how researched facts should be handled.

**Hidden complexity:**

- recognizing tasks where stale model knowledge is unsafe or low quality
- choosing when browsing is required versus optional
- separating user-provided facts, researched facts, assumptions, and recommendations
- requiring citations or source references when external information affects conclusions
- handling local market data, prices, competitors, availability, travel conditions, and other time-sensitive facts
- saying when information is incomplete, ambiguous, or needs real-world validation

**Owns:**

- repo-wide rules for freshness-sensitive work
- citation and source-use expectations
- guidance for distinguishing current facts from assumptions
- expectations for browsing when current or real-time data is required
- patterns for prompting users to validate important findings outside the AI tool

**Does not own:**

- the domain-specific analysis framework for each skill
- the final recommendation or decision artifact
- the browser/tool implementation of a particular AI runtime
- professional advice beyond encouraging appropriate validation

**Key scenarios:**

- A market analysis skill needs current local competitor information and neighborhood context.
- A travel skill needs recent conditions, prices, visa rules, closures, or seasonal constraints.
- A consumer research skill needs current product availability, reviews, and pricing.
- A skill cannot verify a fact and must clearly mark it as uncertain.

**Related modules:**

- Feeds researched facts into `life-skill-experience`.
- Adds source and uncertainty requirements to `artifact-system`.
- Is required by `skill-quality-system` for freshness-sensitive skills.

**Boundary notes:**

This module is not a generic “browser wrapper.” Its depth is in the policy: deciding when current data matters, how facts are represented, and how uncertainty is communicated.

---

### 4. Artifact System

**Suggested slug:** `artifact-system`

**Simple interface / outside promise:** Turn a completed skill workflow into a useful real-world artifact and short action plan.

**Hidden complexity:**

- allowing each skill to own the right output format for its task
- keeping outputs actionable rather than verbose or generic
- making assumptions, risks, sources, and next steps visible
- formatting results so they are useful outside the AI chat
- avoiding one universal template that weakens domain-specific usefulness
- balancing analysis detail with practical readability

**Owns:**

- shared qualities every artifact should have
- artifact expectations such as clarity, actionability, assumption-awareness, and source-awareness when needed
- guidance that each skill chooses its own artifact format
- the expectation that skills end with concrete next actions

**Does not own:**

- one global report template for all skills
- the internal analysis that produces the artifact
- source-gathering rules before the artifact is written
- file storage, publishing, or app-level document management

**Key scenarios:**

- A market analysis skill produces a Markdown opportunity report and validation checklist.
- A buying decision skill produces a comparison matrix and recommendation caveats.
- A travel skill produces a research-backed plan with tradeoffs and open questions.
- A home planning skill produces a household decision checklist or conversation guide.

**Related modules:**

- Receives conclusions from `life-skill-experience`.
- Applies facts and uncertainty from `research-freshness-system`.
- Must satisfy `skill-quality-system`.

**Boundary notes:**

The artifact module should not flatten every skill into the same report. Its job is to protect output usefulness while letting each skill own the template that best fits its purpose.

---

### 5. Skill Discovery and Access

**Suggested slug:** `skill-discovery-and-access`

**Simple interface / outside promise:** Help users understand what skills exist, when to use them, and how to run or install them.

**Hidden complexity:**

- presenting skills by life situation instead of technical structure
- explaining when a skill is appropriate or out of scope
- supporting both agentskills.io installation and repo-root usage
- keeping access guidance lightweight while the product is still a repository
- avoiding premature conversion into a full app or marketplace
- helping users start with plain-language requests instead of internal skill names

**Owns:**

- repository-level skill catalog or README guidance
- usage paths for agentskills.io and direct repo-root AI CLI use
- plain-language descriptions of each skill’s purpose
- boundaries that help users choose the right skill

**Does not own:**

- the internal workflow of a skill
- the exact artifact a skill produces
- agentskills.io as an external product
- a full application UI, marketplace, account system, or runtime platform

**Key scenarios:**

- A user visits the public repo and wants to know which skill fits their situation.
- A user wants to install a skill through agentskills.io.
- A user clones the repo and starts Codex, Gemini, Claude, or Windsurf from the repo root.
- A user wants to invoke a skill with a natural request like “help me analyze this shop idea.”

**Related modules:**

- Surfaces skills built around `life-skill-experience`.
- Communicates expectations from `skill-quality-system`.
- May document when a skill uses `research-freshness-system` or produces artifacts through `artifact-system`.

**Boundary notes:**

This module should stay lightweight for now. It is about finding and running skills, not building a full product interface before the underlying workflows are strong.

## Cross-Module Rules

### User ownership

Every module must preserve the user’s control over the final decision. Skills can guide, recommend, and structure, but they must not pretend to make life decisions for the user.

### Facts, assumptions, and recommendations stay separate

Skills should clearly distinguish user-provided facts, researched facts, assumptions, tradeoffs, recommendations, and next actions.

### Freshness-sensitive work must browse or disclose limits

When a task depends on current information, the skill should use browsing or another current-data capability when available. If it cannot, it must state the limitation and avoid fake certainty.

### Practical output beats impressive prose

The repository should reward artifacts that help users act in the real world, not long responses that sound smart but leave the user unclear about what to do next.

### Skills are for everyday life, not technical work

Technical/coding skills are out of scope for this product. The repo should stay focused on small business, entrepreneurship, home and family planning, travel, consumer research, buying decisions, and similar normal-life domains.

### Professional advice boundaries must be visible

Skills should not present themselves as authoritative legal, medical, financial, safety, or other professional advice. They may help organize thinking and research, but important decisions should include real-world validation when stakes are meaningful.

### Voice is part of quality

The voice should stay warm, grounded, practical, and direct: a nice person helping you think things through, not a corporate assistant or hype machine.

## Boundary Risks to Watch

- **Prompt snippet drift:** New skills may become clever prompts instead of guided workflows. Keep enforcing the `skill-quality-system`.
- **Universal template pressure:** A single artifact format may seem efficient but could weaken skill-specific usefulness. Let each skill own its output template.
- **Research overconfidence:** Skills that use current data must cite, qualify, and separate facts from assumptions.
- **Premature platform building:** Discovery and access should remain lightweight until the skill library itself proves useful.
- **Contributor-centered design drift:** Public PRs may happen, but the core design should continue optimizing for users consuming high-quality maintained skills.
