# Step: Create skill instructions

## Goal

Create the Codex-compatible Initial Market Analysis skill with valid frontmatter, trigger description, clarification-first workflow, mandatory freshness research behavior, final report contract, and scope boundaries.

## Scope

- Create `.agents/skills/initial-market-analysis/SKILL.md`.
- Include valid skill frontmatter with `name: initial-market-analysis` and a clear plain-language description.
- Define a one-question-at-a-time clarification workflow that prevents analysis before the business idea, location, target customer, offer, and decision goal are clear.
- Require browsing for current, location-specific evidence before making current market claims when browsing is available.
- Define analysis expectations and the final Initial Market Analysis Report structure from the technical design.
- Include source reliability, professional-advice, and out-of-scope boundaries.
- Do not create README, catalog, agentskills.io, application code, tests, or runtime tooling.

## Files

- `.agents/skills/initial-market-analysis/SKILL.md`

## Done when

- `.agents/skills/initial-market-analysis/SKILL.md` exists.
- The skill file has valid Markdown skill frontmatter with `name: initial-market-analysis`.
- The description matches plain-language market validation or initial market analysis requests for local or small-area business ideas.
- The workflow requires focused clarification before research and final output.
- The workflow requires browsing for current market evidence when browsing is available.
- The workflow separates user-provided facts, researched facts, assumptions, risks, and recommendations.
- The final report contract includes snapshot verdict, business idea summary, target location, target customers, evidence reviewed, demand signals, competitor landscape, differentiation opportunities, risks and assumptions, source reliability notes, validation experiments, and next actions.
- The skill includes explicit out-of-scope and professional-advice boundaries.
## Review status

- Status: approved
- Approved by: juanca
- Approved at: 2026-05-19T13:31:28-06:00
