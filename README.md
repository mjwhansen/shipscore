# SHIP Score

A dead-simple prioritization framework for indie founders and small teams.

**SHIP Score = Strategic Heft + Income - Perspiration**

Instead of gut-feel prioritization, SHIP forces you to consider three things for every feature, bug, or idea:

- **Strategic Heft** (1-5): Competitive advantage. Does this differentiate us in ways customers care about?
- **Income** (1-5): Revenue potential. Will people pay *us* for this? Will *not* doing it lose us money? How certain are we?
- **Perspiration** (1-5): Engineering effort. How much engineering effort, QA, and ongoing maintenance does this require? (Subtracted from total)

Scores range from **-3** (worst) to **+11** (best). The end result is a rank-ordered list of everything you could work on, allowing you to go from an endless pile of issues and prioritization based on recency to clearly seeing which issues have high ROI.

## What's in this repo

- **`ship_framework.md`** — The full scoring framework with definitions, key questions, common traps, and interpretation guidelines
- **`score.md`** — A Claude Code / AI assistant skill that conducts structured interviews to score features against the framework

## Using the scoring skill

The `score.md` file is designed to work as a [Claude Code custom command](https://docs.anthropic.com/en/docs/claude-code/tutorials/custom-slash-commands) or as instructions for any AI assistant.

### With Claude Code

1. Copy `score.md` and `ship_framework.md` into your project's `.claude/commands/` directory (or wherever you keep custom commands)
2. Run `/score` to start a scoring session

### With any AI assistant

Paste the contents of `ship_framework.md` and `score.md` into your system prompt or project context. Then ask the assistant to score a feature.

### On your own

Just read `ship_framework.md` and score features yourself. The framework works fine with a spreadsheet and 5 minutes of honest thought per feature.

## Quick reference

| SHIP Score | Interpretation | Action |
|-----------|---------------|---------|
| **6+** | Excellent — high impact, clear win | Prioritize |
| **3-5** | Good — solid features worth building | Candidate |
| **0-2** | Medium — questionable ROI | Revisit when context changes |
| **Negative** | Low — poor ROI | Park or defer indefinitely |

## Credits

The SHIP Score framework was created by [Michele Hansen](https://bsky.app/profile/mjwhansen.com), author of [*Deploy Empathy: A Practical Guide to Interviewing Customers.*](https://www.amazon.com/Deploy-Empathy-practical-interviewing-customers/dp/173744660X).

Massive thanks to [Ben Aldred](https://www.linkedin.com/in/benaldred/), founder of user research operations platform [Participant Kit](https://participantkit.com/), for sharing the Claude Code skill he made based on the framework as well as adding the "Common Traps" concept to the scoring framework. His skill serves as the basis of this skill. 

## License

MIT
