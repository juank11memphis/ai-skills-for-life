# Initial Market Analysis Skill Feature Brief

## Summary

The Initial Market Analysis skill helps a user assess an early local business idea before they invest serious time, money, or emotion into it. The skill interviews the user until the idea is specific enough, browses for current market signals, and produces an evidence-aware Markdown report with demand signals, competitors, differentiation opportunities, risks, assumptions, and practical validation steps.

This is not a full business plan. It is a guided first-pass market analysis that helps the user decide whether an idea is worth validating further.

## Product Vision Fit

This feature directly supports AI Skills For Life’s promise: turning vague real-life goals into structured AI-assisted workflows that produce useful artifacts. A user may arrive with an idea like “I want to open a coffee shop” or “I’m thinking of starting a small service business.” The skill should help them narrow the idea, gather relevant context, research current conditions, and leave with a clearer next move.

The feature fits the product’s small business and entrepreneurship focus while protecting the repo’s boundaries: it provides structured thinking and real-world validation guidance, not authoritative business, legal, financial, or investment advice.

## Deep Module Fit

- **Life Skill Experience (`life-skill-experience`)**: owns the guided interview and end-to-end workflow from vague business idea to useful market analysis.
- **Research Freshness System (`research-freshness-system`)**: owns the requirement to browse for current, location-specific, source-aware market information.
- **Artifact System (`artifact-system`)**: owns the expectation that the skill ends with a practical Markdown report and short action plan.
- **Skill Quality System (`skill-quality-system`)**: constrains the skill so it remains structured, honest about uncertainty, non-generic, and user-controlled.
- **Skill Discovery and Access (`skill-discovery-and-access`)**: will later help users find and invoke this skill by plain-language business situations.

## User / Customer Problem

People often get excited about a business idea before understanding the market around it. They may not know what to research, how specific their idea needs to be, who their likely customers are, what competitors already exist, or what real-world signals would make the idea more or less promising.

A one-off AI chat can produce generic advice, but it usually depends on the user knowing what to ask. This skill should do the harder work: extract the needed context, push for specificity, gather fresh information, and turn the analysis into a usable next-step artifact.

## Business Goal

Create the first high-value AI Skills For Life skill in the small business / entrepreneurship domain. It should demonstrate the repo’s core product pattern: guided questioning, current research, clear assumptions, useful artifacts, and practical real-world next actions.

## Target User / Scenario

The target user is an AI-curious person who can run a skill through agentskills.io or from the repo root in an AI agent environment. They are considering a local or small-area business idea and want an initial market read before committing further.

Typical scenario:

> “I’m thinking about opening or starting X in location Y. Help me understand whether this market looks promising and what I should validate next.”

The skill should work best when the user has, or can be guided to clarify:

- the business idea
- the specific location or market area
- the likely customer
- the offer, product, or service
- their known assumptions, constraints, timeline, or goals

## Proposed Experience

The skill should behave like a focused interviewer before it behaves like an analyst.

It should ask one question at a time, provide recommended defaults or examples when helpful, and keep asking until the idea is scoped enough for meaningful research. It should push the user toward focused answers, especially around location and customer. If the user gives a broad location, the skill should narrow it unless the business is clearly regional or online.

Once the idea is clear enough, the skill should browse broadly for fresh, relevant information. It should prefer practical public sources such as local search results, maps-style competitor listings, competitor websites, social pages, review platforms, local directories, public statistics, local news, trend sources, pricing/menu/service pages, and accessible community or social signals. Less reliable sources can be used, but the skill must label their limits.

The final output should be an Initial Market Analysis Report that gives the user a grounded read on the idea without pretending to guarantee success.

## MVP Scope

- Interview the user one question at a time until the business idea is specific enough to analyze.
- Require a user-specified location or market area and push for a narrow scope when needed.
- Clarify the offer, target customer, business type, constraints, and decision the user is trying to make.
- Browse for fresh, location-specific, source-aware market information.
- Research demand signals, competitor landscape, customer segments, substitutes, pricing or offer patterns when available, and local context.
- Clearly separate user-provided facts, researched facts, assumptions, risks, and recommendations.
- Produce a Markdown Initial Market Analysis Report with:
  - business idea summary
  - target location / market area
  - target customers
  - demand signals
  - competitor landscape
  - differentiation opportunities
  - risks and assumptions
  - source notes and reliability caveats
  - recommended validation experiments
  - lightweight verdict: Promising, Mixed, High Risk, or Insufficient Evidence
- End with concrete next steps the user can take outside the AI tool.

## Out of Scope

- Full business plan creation
- Detailed financial projections
- Legal, regulatory, tax, accounting, or professional advice
- Lease negotiation or location acquisition advice
- Branding package or marketing campaign creation
- Operations plan
- Funding, investor, or pitch materials
- Guaranteed yes/no decision about whether to open the business
- National-scale startup market sizing unless the user’s idea is explicitly not local

## Success Signals

- The user finishes with a clearer, evidence-backed understanding of whether the business idea is worth validating further.
- The final report contains current market signals and clearly marked source limitations.
- The user can name the riskiest assumptions behind the idea.
- The user has concrete validation actions they can perform in the real world.
- The skill feels more useful than asking a generic AI chat for “market analysis.”

## Business-Level Acceptance Criteria

- The skill does not produce a final report before it has clarified the business idea, location, target customer, and offer enough for meaningful analysis.
- The skill asks focused questions one at a time and pushes for specificity instead of accepting vague inputs too quickly.
- The skill uses browsing for fresh information before making market claims that depend on current conditions.
- The skill labels source quality or reliability when information comes from weaker, indirect, or anecdotal sources.
- The skill distinguishes researched evidence from assumptions and recommendations.
- The skill provides a lightweight verdict with caveats, not a fake precise score or guaranteed decision.
- The skill ends with practical validation experiments and next steps.
- The skill avoids presenting itself as professional legal, financial, accounting, tax, or investment advice.

## Risks / Tradeoffs

- **Research quality varies by location.** Some markets will have sparse online data, so the skill must be comfortable saying when evidence is limited.
- **Browsing can create false confidence.** The skill must cite, qualify, and explain source limits rather than treating search results as complete truth.
- **Users may want a yes/no answer.** The skill should give a useful verdict while reinforcing that early market analysis is not a guarantee.
- **Broad ideas weaken output quality.** The skill must keep interviewing until the idea is focused enough.
- **Scope creep is likely.** Market analysis can easily expand into business planning, branding, finance, legal, or operations. The MVP should stay focused on initial market understanding and validation next steps.
