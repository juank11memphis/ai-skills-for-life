# Create the Initial Market Analysis Skill

## Epic

[Initial Market Analysis Skill](../epic_brief.md)

## User Story

As an AI Skills For Life user, I want to invoke an Initial Market Analysis skill for a local business idea, so that I can clarify the idea, review current market evidence, and decide what to validate next.

## Context

The feature brief defines a guided first-pass market analysis for local or small-area business ideas. The technical design specifies a Codex-compatible skill at `.agents/skills/initial-market-analysis/SKILL.md` so the workflow works immediately when a user clones the repo and starts Codex from the repo root.

## Scope

- Create `.agents/skills/initial-market-analysis/SKILL.md`.
- Add valid skill frontmatter with the `initial-market-analysis` name and a clear user-facing description.
- Define a clarification-first workflow that asks one question at a time.
- Require the skill to keep interviewing until the business idea, location, target customer, offer, and decision goal are specific enough.
- Require narrow location scoping unless the business is explicitly regional or online.
- Require browsing for current, location-specific evidence before making market claims.
- Instruct the skill to label weaker or anecdotal sources clearly.
- Define analysis expectations for demand signals, competitors, substitutes, customer segments, offer/pricing patterns, local context, risks, and differentiation opportunities.
- Define the final Initial Market Analysis Report structure.
- Include a lightweight verdict of Promising, Mixed, High Risk, or Insufficient Evidence.
- Include out-of-scope handling for business planning, finance, legal, lease, branding, operations, funding, and guaranteed yes/no decisions.

## Out of Scope

- Creating a separate public skill catalog.
- Publishing to agentskills.io.
- Adding README discovery documentation.
- Building application code, tests, commands, or runtime tooling.
- Expanding into full business plan, financial projection, legal, operations, branding, or funding workflows.

## Acceptance Criteria

- `.agents/skills/initial-market-analysis/SKILL.md` exists.
- The skill file has valid Markdown skill frontmatter with `name: initial-market-analysis`.
- The description clearly matches plain-language requests for market validation or initial market analysis of a local or small-area business idea.
- The workflow tells the assistant to ask one focused question at a time before analysis.
- The workflow prevents final report generation until the required context is clear enough.
- The workflow requires browsing for current market evidence when browsing is available.
- The workflow tells the assistant to separate user-provided facts, researched facts, assumptions, risks, and recommendations.
- The final report contract includes snapshot verdict, business idea summary, target location, target customers, evidence reviewed, demand signals, competitor landscape, differentiation opportunities, risks and assumptions, source reliability notes, validation experiments, and next actions.
- The skill includes explicit out-of-scope and professional-advice boundaries.

## Validation

- Inspect the created skill file for valid frontmatter and expected sections.
- Manually verify the skill can be matched by requests such as “help me validate this shop idea” or “do an initial market analysis for my business idea.”
- Manually verify the skill requires clarification before research.
- Manually verify the skill requires browsing before current market claims.
- Manually verify the final report structure matches the technical design.

## Notes

- Use `ai-prompt-engineer-master` during implementation to keep the skill concise and behaviorally strong.
- Use `clean-code` only if implementation adds or modifies code; this story is expected to be Markdown-only.
