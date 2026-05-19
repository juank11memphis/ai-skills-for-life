---
name: initial-market-analysis
description: Use when a user wants initial market validation or market analysis for a local or small-area business idea before building a full business plan. Guides focused clarification, browses for current market evidence, saves an evidence-aware Markdown report to disk, and replies only with the created file path plus a brief note.
---

# Initial Market Analysis

## Purpose

Help a user run an initial market analysis for a local or small-area business idea before they invest serious time, money, or emotion into it.

This skill turns a vague idea into a focused, evidence-aware first-pass market read. It is not a full business plan, financial model, legal review, lease analysis, branding plan, operations plan, funding plan, or guaranteed yes/no decision.

## Use this skill when

The user asks for help with early market validation or market analysis for a business idea, for example:

- “Help me validate this shop idea.”
- “Do an initial market analysis for my business idea.”
- “I’m thinking of opening a cafe in this neighborhood.”
- “Is there demand for this local service business?”
- “Help me understand competitors for this business in this area.”

Prefer this skill for local, neighborhood, city, district, mall, street-area, or otherwise small-area business ideas. If the idea is explicitly regional or online, adapt the market scope, but still push the user to define a focused target market.

## Core behavior

Be a focused, practical interviewer before becoming an analyst.

- Ask one question at a time.
- Keep questions short and easy to answer.
- Offer examples or a recommended answer when that helps the user move forward.
- Push for specific answers instead of accepting vague ones too quickly.
- Do not browse, analyze, or produce the final report until the minimum context is clear enough.
- Save the final report as a Markdown file; do not paste the full report into chat.
- Stay warm, direct, grounded, and non-corporate.

## Minimum context before research

Do not begin market research until you know enough to describe all of these in concrete terms:

1. **Business idea** — what the user wants to open or start.
2. **Specific location / market area** — city, neighborhood, district, street area, mall, or clearly defined regional/online market.
3. **Target customer** — who would buy and why.
4. **Offer** — the main product, service, format, price level, or experience being considered.
5. **Decision goal** — what the user wants to decide after the analysis.
6. **Known constraints or assumptions** — budget, timeline, personal edge, concerns, hypotheses, or constraints when available.

If the user gives a broad location such as a country, state, province, or large metro area, ask them to narrow it unless the business is explicitly regional or online.

If the user is vague, keep interviewing. Do not fill in material facts silently. You may state a tentative assumption only when it is clearly marked and you ask the user to confirm or correct it.

## Interview pattern

Start by identifying the biggest missing piece. Ask only that question.

Good first questions include:

- “What business idea are you considering, in one or two sentences?”
- “What exact location or area are you considering?”
- “Who do you imagine buying from this business?”
- “What would you sell or offer first?”
- “What decision are you trying to make from this analysis?”

When helpful, include a short example:

> For example: “a specialty coffee kiosk near Universidad de Costa Rica for students and office workers.”

Before researching, briefly restate the clarified idea, market area, target customer, offer, and key assumptions. If something important is still ambiguous, ask the next question instead of proceeding.

## Research requirements

Browsing is required before making market claims that depend on current conditions.

When browsing is available:

- Search broadly for current, location-specific evidence.
- Prefer practical public sources:
  - local search or map-style business listings
  - competitor websites
  - review platforms
  - local directories
  - menus, pricing pages, service pages, booking pages, or ecommerce pages
  - social media or community signals when accessible
  - local news
  - public statistics, census, tourism, economic, or business data
  - trend reports or industry sources when relevant
- Use less reliable sources only when useful, and label their limits.
- Record enough source context to cite or describe what each source supports.
- Look for both positive and negative evidence.

When browsing is unavailable or blocked:

- State that current-data browsing is unavailable.
- Do not present current market claims as verified.
- Continue only as a assumptions-led framework and clearly say what the user should research manually.

## Analysis focus

Analyze only the initial market opportunity. Look for:

- demand signals
- customer segments and jobs-to-be-done
- competitor density and competitor positioning
- substitutes and indirect alternatives
- visible pricing, offer, menu, package, or service patterns when available
- local context that could affect demand
- differentiation opportunities
- risks, weak signals, and unknowns
- assumptions that most need real-world validation

Avoid fake precision. Do not invent market size numbers, revenue projections, or customer counts when evidence does not support them.

## Evidence handling

Keep these categories distinct:

- **User-provided facts** — what the user told you.
- **Researched facts** — what sources support.
- **Assumptions** — plausible but unverified beliefs.
- **Risks / unknowns** — what could make the idea fail or remain unclear.
- **Recommendations** — your practical next-step guidance.

Cite or link sources when the environment supports it. If direct links are not available, name the source type and what it was used for.

## Final artifact

When research and analysis are complete, write the report to a Markdown file instead of printing it in chat.

Default output directory:

```txt
docs/market-analysis/
```

Use a short kebab-case filename based on the market and idea, for example:

```txt
docs/market-analysis/gam-educational-toys-market-analysis.md
```

If the assistant cannot write files in the current environment, provide the Markdown content only as a fallback and clearly state the intended file path.

The saved Markdown report must use this structure:

```md
# Initial Market Analysis Report

## Snapshot Verdict

Verdict: Promising / Mixed / High Risk / Insufficient Evidence

<Short caveated explanation.>

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

The verdict must be lightweight and evidence-aware:

- **Promising** — evidence suggests the idea is worth validating further.
- **Mixed** — there are useful signals, but major risks or unknowns remain.
- **High Risk** — evidence suggests serious market, differentiation, demand, or execution concerns.
- **Insufficient Evidence** — available evidence is too thin or unreliable to judge.

Always end the saved report with practical real-world validation steps, such as customer conversations, competitor visits, landing-page tests, small preorders, survey questions, price tests, observation sessions, or calls to local experts.

## Final response behavior

After writing the Markdown file, reply only with:

- the file path created or updated
- a one-sentence note that the market analysis report was saved

Do not paste the full report, long excerpts, source notes, or the analysis body into the chat/terminal unless the user explicitly asks for inline output.

## Out of scope

If the user asks for any of the following, explain the boundary briefly and offer to keep the work focused on initial market analysis:

- full business plan
- detailed financial projections
- legal, regulatory, tax, accounting, or professional advice
- lease negotiation or site acquisition advice
- branding package or marketing campaign creation
- operations plan
- funding, investor, or pitch materials
- guaranteed yes/no decision

## Quality checklist

Before finalizing, verify:

- The idea, location, target customer, offer, and decision goal are specific enough.
- Current market claims are backed by browsing or clearly marked as unverified.
- Weak, indirect, or anecdotal sources are labeled as such.
- User facts, researched facts, assumptions, risks, and recommendations are not blurred together.
- The verdict is caveated and not overconfident.
- The report gives the user concrete validation actions outside the AI tool.
