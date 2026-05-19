# Technical Design: Initial Market Analysis Skill

## Inputs

- Product vision: `docs/product-vision.md`
- Deep Module Map: `docs/deep-module-map.md`
- Feature brief: `docs/features/initial-market-analysis/feature_brief.md`
- Delegated skills for later implementation: `ai-prompt-engineer-master`, `clean-code`

## Summary

Implement the feature as a Codex-compatible skill under `.agents/skills/initial-market-analysis/SKILL.md` so it works immediately when a user clones the repo and starts Codex from the repo root. The skill should be a structured workflow instruction file, not application code: it must interview the user until the business idea is specific enough, require browsing for current market evidence, and produce a source-aware Initial Market Analysis Report.

## Existing Context

This repository currently contains:

- repo workflow skills in `.agents/skills/`
- `.codex/config.toml` pointing Codex to `../AGENTS.md`
- product planning docs under `docs/`
- no separate public `skills/` catalog yet

For this first life skill, the user explicitly wants the skill to live in `.agents/skills/` for out-of-the-box repo-root usage, even though longer-term public catalog organization may change.

## Proposed Design

### Skill Location

Create the skill at:

```txt
.agents/skills/initial-market-analysis/SKILL.md
```

Use the skill name:

```txt
initial-market-analysis
```

This keeps the MVP simple: clone repo, start Codex at repo root, invoke the skill naturally.

### Skill Metadata

The skill frontmatter should describe the user-facing trigger clearly, for example:

```yaml
---
name: initial-market-analysis
description: Use when a user wants initial market validation or market analysis for a local or small-area business idea before building a full business plan. Guides the user through focused clarification, browses for current market evidence, and produces an evidence-aware Initial Market Analysis Report with risks and validation next steps.
---
```

The description should emphasize:

- initial market analysis / validation
- local or small-area business ideas
- current browsing requirement
- not a full business plan or professional advice

### Workflow Shape

The skill should be written as an instruction-first workflow with these phases:

1. **Clarify before researching**
   - Ask one question at a time.
   - Keep interviewing until the business idea, location, target customer, offer, and decision goal are specific enough.
   - Push for narrow, focused answers.
   - If the location is broad, ask the user to narrow it unless the idea is explicitly regional or online.
   - Use recommended answers or examples when helpful.

2. **Confirm readiness to research**
   - Briefly restate the understood idea, market area, target customer, and key assumptions.
   - Do not ask for a formal approval gate unless the user’s answer is ambiguous; proceed once the minimum context is clear.

3. **Browse for current evidence**
   - Browsing is mandatory before making market claims that depend on current conditions.
   - Search broadly across practical public sources: local search/map-style listings, competitor websites, review platforms, local directories, public statistics, social/community signals when accessible, local news, trend sources, and pricing/menu/service pages.
   - Use weaker sources when useful, but label reliability limits.
   - If browsing is unavailable, state that limitation and avoid presenting current market claims as verified.

4. **Analyze evidence**
   - Separate user-provided facts, researched facts, assumptions, risks, and recommendations.
   - Look for demand signals, competitor density, substitutes, customer segments, pricing/offer patterns, local context, and differentiation opportunities.
   - Avoid fake precision and overconfident market sizing.

5. **Produce final artifact**
   - Output a Markdown Initial Market Analysis Report.
   - Include a lightweight verdict: `Promising`, `Mixed`, `High Risk`, or `Insufficient Evidence`.
   - End with concrete validation experiments and next actions.

### Report Contract

The final report should include these sections unless the user’s scenario makes a section irrelevant:

```md
# Initial Market Analysis Report

## Snapshot Verdict

## Business Idea Summary

## Target Location / Market Area

## Target Customers

## Evidence Reviewed

## Demand Signals

## Competitor Landscape

## Differentiation Opportunities

## Risks and Assumptions

## Source Reliability Notes

## Recommended Validation Experiments

## Next Actions
```

The artifact format belongs to this skill, but it must follow the repo-wide artifact expectations: clear, actionable, assumption-aware, source-aware, and useful outside the AI chat.

### Deep Module Translation

- `life-skill-experience`: implemented through the skill’s one-question-at-a-time interview, readiness threshold, analysis flow, and warm practical voice.
- `research-freshness-system`: implemented through explicit mandatory browsing rules, source reliability notes, and separation of current evidence from assumptions.
- `artifact-system`: implemented through the Initial Market Analysis Report contract and next-action ending.
- `skill-quality-system`: implemented through strong trigger boundaries, out-of-scope rules, caveats, and prevention of generic market-analysis output.
- `skill-discovery-and-access`: supported indirectly by placing the skill in `.agents/skills/` for repo-root Codex usage. Broader catalog/readme work can come later.

### Boundaries and Non-Goals

The skill must not produce:

- a full business plan
- detailed financial projections
- legal, regulatory, tax, accounting, or investment advice
- lease or negotiation advice
- branding or marketing campaign assets
- operations plans
- funding or pitch materials
- a guaranteed yes/no decision

If the user asks for those, the skill should explain that they are out of scope and offer to keep the output focused on initial market analysis and validation steps.

## Validation

Because this feature is a Markdown skill, validation should focus on behavior and repo compatibility:

- Confirm `.agents/skills/initial-market-analysis/SKILL.md` exists with valid frontmatter.
- Confirm the skill description is triggerable by plain-language market validation requests.
- Manually review that the workflow requires clarification before research.
- Manually review that browsing is required for current market claims.
- Manually review that the final report contract includes evidence, risks, source reliability, verdict, validation experiments, and next actions.
- Run `sibu doctor` only if workflow-managed files change or validation of Sibu state is needed; this feature should not modify Sibu-managed templates.

## Risks / Tradeoffs

- **Location choice is intentionally pragmatic.** `.agents/skills/` gives immediate repo-root usefulness, but it mixes product life skills with repo workflow skills. A future discovery/access feature may move or mirror public skills into a cleaner catalog.
- **Skill behavior depends on the host agent.** Browsing support and source presentation may vary between Codex, Gemini, Claude, Windsurf, and agentskills.io environments.
- **Long instruction files can become vague.** The implementation should keep the skill direct and operational, using `ai-prompt-engineer-master` to make the prompt concise without weakening behavior.
- **Market analysis can sprawl.** The skill must enforce initial-analysis boundaries and redirect business-plan, finance, legal, and operations requests out of MVP scope.
