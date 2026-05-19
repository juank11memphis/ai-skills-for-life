# AI Skills For Life

Reusable AI skills that help you think through practical life decisions and leave with a useful next step.

AI Skills For Life is a collection of guided AI workflows you can run with an AI agent such as Codex, Gemini CLI, Claude, Windsurf, or another tool that can read local skill instructions.

Instead of giving you a one-off answer, each skill is meant to guide you through a real situation: it asks focused questions, helps gather the right context, uses current information when needed, and produces something you can actually use — a report, checklist, comparison, plan, or next-action guide.

## What you can do with this repo today

This repo is early and intentionally small. Right now, it includes one user-facing skill:

### Initial Market Analysis

Use this when you are considering a local or small-area business idea and want a first-pass market read before investing serious time, money, or emotion.

You can ask things like:

- “Help me validate this shop idea.”
- “I’m thinking of opening a coffee kiosk near a university. Help me understand the market.”
- “I want to start a small service business in this neighborhood. What should I validate first?”

The skill will help you:

1. Clarify the business idea, location, target customer, offer, and decision goal.
2. Research current market signals when needed.
3. Understand demand signals, competitors, risks, assumptions, and possible differentiation.
4. Save a Markdown market analysis report under `docs/market-analysis/`.
5. Leave with practical validation experiments and next actions.

Skill file: [`initial-market-analysis/SKILL.md`](.agents/skills/initial-market-analysis/SKILL.md)

Example report: [`docs/market-analysis/gam-educational-toys-market-analysis.md`](docs/market-analysis/gam-educational-toys-market-analysis.md)

## Who this is for

This repo is for people who want AI to act like a structured thinking partner for real-life decisions.

It is currently best for people who are comfortable cloning a repository, opening it in an AI agent environment, and asking for a skill in plain language. The workflows are written for everyday decisions and practical next steps.

## How to use it

### 1. Clone the repo

```bash
git clone <repo-url>
cd ai-skills-for-life
```

### 2. Open it in your AI agent tool

Use an AI environment that can read this repository and its `.agents/skills/` folder.

### 3. Ask for the skill in plain language

For example:

```text
Use the initial-market-analysis skill to help me validate a business idea.
```

or:

```text
I’m thinking about opening a specialty coffee kiosk near a university. Help me run an initial market analysis.
```

The skill should interview you before analyzing. If it asks follow-up questions, answer as concretely as you can — the better the context, the better the final artifact.

## What to expect from a skill

A good skill in this repo should:

- ask clear questions instead of expecting you to know the perfect prompt
- help you narrow a vague idea into something specific enough to evaluate
- use current information when the decision depends on current facts
- clearly separate facts, assumptions, risks, and recommendations
- create a practical artifact you can reuse outside the chat
- end with next steps you can take in the real world

## Current project state

This is an MVP-stage repository. It is public-ready for people who want to try the current skill and follow the project, but it is not yet a large library.

Included today:

- Product vision: [`docs/product-vision.md`](docs/product-vision.md)
- Skill design map: [`docs/deep-module-map.md`](docs/deep-module-map.md)
- Initial Market Analysis skill: [`.agents/skills/initial-market-analysis/SKILL.md`](.agents/skills/initial-market-analysis/SKILL.md)
- Feature planning docs under [`docs/features/`](docs/features/)
- Example/generated market analysis reports under [`docs/market-analysis/`](docs/market-analysis/)

Not included yet:

- a large catalog of life skills
- a polished app interface
- a formal contribution system
- professional advice or guaranteed decisions

## Repository structure

```text
.
├── .agents/skills/                 # Skill instructions
│   └── initial-market-analysis/     # Current public life skill
├── docs/
│   ├── product-vision.md            # What this project is trying to become
│   ├── deep-module-map.md           # How skills should be designed
│   ├── features/                    # Feature planning docs
│   └── market-analysis/             # Example/generated reports
├── AGENTS.md                        # Instructions for AI agents working in this repo
└── README.md
```

## Roadmap direction

The goal is to grow this into a practical collection of everyday decision workflows.

Likely future skill areas include:

- small business and entrepreneurship
- consumer research and buying decisions
- travel planning and research
- home and family planning

The priority is quality over quantity: each skill should guide the user, use the right context, and produce something useful.

## Suggesting a skill

If you have an idea for a skill, describe:

- the real-life situation it helps with
- who would use it
- what decision or task it supports
- what artifact it should produce
- what information it should ask for first
- what real-world validation it should encourage

## Safety and limitations

AI Skills For Life can help you structure thinking, research, and next steps, but it should not be treated as the final authority.

For important decisions, validate the output with real people, current sources, personal constraints, and qualified professionals where appropriate. Do not use this repo as a substitute for professional legal, medical, financial, tax, accounting, safety, or investment advice.

## License

No license file is currently included. Until one is added, assume all rights are reserved by the repository owner.
