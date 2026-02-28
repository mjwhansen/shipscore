# The SHIP Score

A dead-simple prioritization framework for indie founders and small teams.

**SHIP Score = Strategic Heft + Income - Perspiration**

Instead of gut-feel prioritization, SHIP forces you to consider three things for every feature, bug, or idea:

- **Strategic Heft** (1-5): Competitive advantage. Does this differentiate us in ways customers care about?
- **Income** (1-5): Revenue potential. Will people pay *us* for this? Will *not* doing it lose us money? How certain are we?
- **Perspiration** (1-5): Engineering effort. How much engineering effort, QA, and ongoing maintenance does this require? (Subtracted from total)

Scores range from **-3** (worst) to **+11** (best). The end result is a rank-ordered list of everything you could work on, allowing you to go from an endless pile of issues and prioritization based on recency to clearly seeing which issues have high ROI.

## What's in this repo

This repo is an [Agent Skill](https://agentskills.io) — a portable package of instructions and reference material that any compatible AI agent can discover and use.

```
ship-score/
├── SKILL.md                        # Agent skill definition (instructions + frontmatter)
├── references/
│   └── ship_framework.md           # Full scoring framework with definitions and guidance
├── README.md
└── license.md
```

- **`SKILL.md`** — The skill that conducts structured interviews to score features against the framework
- **`references/ship_framework.md`** — The full scoring framework with definitions, key questions, common traps, and interpretation guidelines

## Using the skill

### With any Agent Skills-compatible agent

This skill works with any agent that supports the [Agent Skills open standard](https://agentskills.io), including Claude Code, Cursor, Goose, Amp, VS Code, GitHub Copilot, OpenAI Codex, and [many others](https://agentskills.io/home).

Clone or copy this repo into wherever your agent discovers skills, then ask the agent to score a feature. The agent will load the skill automatically when it matches your request.

### With Claude Code

1. Copy the `ship-score` directory (containing `SKILL.md` and `references/`) into your project's `.claude/skills/` directory
2. Ask Claude to score a feature, prioritize a backlog item, or run `/ship-score`

### With any AI assistant

Paste the contents of `references/ship_framework.md` and `SKILL.md` into your system prompt or project context. Then ask the assistant to score a feature.

### On your own

Just read `references/ship_framework.md` and score features yourself. The framework works fine with a spreadsheet and 5 minutes of honest thought per feature.

## Quick reference

| SHIP Score | Interpretation | Action |
|-----------|---------------|---------|
| **6+** | Excellent — high impact, clear win | Prioritize |
| **3-5** | Good — solid features worth building | Candidate |
| **0-2** | Medium — questionable ROI | Revisit when context changes |
| **Negative** | Low — poor ROI | Park or defer indefinitely |

## Credits

The SHIP Score framework was created by **[Michele Hansen](https://bsky.app/profile/mjwhansen.com)**, CEO & Co-Founder of [Geocodio](https://www.geocod.io) and author of [*Deploy Empathy: A Practical Guide to Interviewing Customers.*](https://www.amazon.com/Deploy-Empathy-practical-interviewing-customers/dp/173744660X).

Massive thanks to **[Ben Aldred](https://www.linkedin.com/in/benaldred/)**, founder of user research operations platform [Participant Kit](https://participantkit.com/), for sharing the Claude Code skill he made based on the framework, for testing the framework over many months and providing helpful feedback, and adding the "Common Traps" concept to the scoring framework. His skill serves as the basis of this skill. Thanks for all of your feedback and collaboration, Ben!

## License

MIT
