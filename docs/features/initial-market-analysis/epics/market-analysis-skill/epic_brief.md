# Initial Market Analysis Skill Epic Brief

## Summary

Deliver the first AI Skills For Life user-facing skill: an Initial Market Analysis skill that works out of the box from the repo root in Codex. The Epic is complete when a user can invoke the skill for a local or small-area business idea, be interviewed until the idea is specific enough, and receive a source-aware Initial Market Analysis Report with risks, verdict, validation experiments, and next actions.

## Source Context

- Feature brief: `../../feature_brief.md`
- Technical design: `../../technical_design.md`

## Scope

- Create `.agents/skills/initial-market-analysis/SKILL.md`.
- Define clear skill metadata and trigger behavior.
- Encode the one-question-at-a-time clarification workflow.
- Require browsing for current, location-specific market claims.
- Define the final Markdown report contract.
- Include out-of-scope boundaries and professional-advice caveats.
- Validate the skill file and behavior expectations manually.

## Out of Scope

- A separate public `skills/` catalog.
- README or agentskills.io publishing work.
- Full business planning, finance, legal, operations, branding, lease, funding, or pitch-material workflows.
- Automated tests beyond checks appropriate for a Markdown skill file.

## User Stories

- [Create the Initial Market Analysis skill](./stories/01-create-initial-market-analysis-skill.md)

## Acceptance Criteria

- The skill exists at `.agents/skills/initial-market-analysis/SKILL.md` with valid skill frontmatter.
- The skill can be discovered by a plain-language request for initial market validation or market analysis.
- The workflow requires focused clarification before research and final output.
- The workflow requires browsing before making current market claims when browsing is available.
- The final artifact contract includes evidence, source reliability, risks, verdict, validation experiments, and next actions.
- The skill enforces MVP boundaries and avoids presenting itself as professional advice.

## Dependencies / Risks

- The skill depends on host-agent support for skills and, for best results, browsing.
- `.agents/skills/` intentionally mixes repo workflow skills with public life skills for MVP convenience.
- Research quality varies by location, so the skill must handle sparse evidence honestly.
