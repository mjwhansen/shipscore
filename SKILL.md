---
name: ship-score
description: Conduct a SHIP interview to score and prioritize a product feature or bug. Use when the user runs /ship-score, asks to "score a feature", "prioritize the backlog", or wants to interview and score product features using the SHIP framework (Strategic Heft + Income - Perspiration).
license: MIT
metadata:
  author: michele-hansen
  version: "2026-02-27"
---

# SHIP Score

Conduct an in-depth interview to score product features using the SHIP framework. Goal: reach **90-95% confidence** on each dimension before proposing scores.

## CRITICAL: Read the Framework First

**BEFORE doing anything else, read [the SHIP framework](references/ship_framework.md).**

This is the canonical source for all scoring definitions. Read it at the start of every scoring session and keep it in context throughout. Do not rely on memory or summaries — the exact definitions, score tiers, common traps, and key questions matter.

## Process

1. **Read [references/ship_framework.md](references/ship_framework.md)** — mandatory first step, every session
2. Ask the user what feature, bug, or idea they want to score (or let them paste a description)
3. Display feature context as an index card
4. Interview for each dimension until 90-95% confident
5. Propose scores with reasoning
6. Confirm with user, adjust if needed
7. Present final scorecard

## Interview Principles

- **Start at 0% confidence** for every feature, every dimension
- **Push back on vague answers** — "could help" is not validated demand
- **Challenge assumptions** — "I think customers want this" needs evidence
- **Track confidence explicitly** throughout — say where you are ("that gets me to ~60%...")
- **Don't settle for gut feelings** — dig for specific examples, data, customer names
- **Reference the framework definitions** when explaining why a score lands where it does
- **Use the Key Questions and Common Traps** from the framework to guide the interview — these are there to prevent scoring mistakes

## Interview Workflow

### Opening

Display the feature as an ASCII index card:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  Feature / Bug Title                                                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Description or context provided by the user                                │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

Then state: **"Starting at 0% confidence on all three dimensions. Let's dig in."**

If the user provides an issue tracker link or ID, include it at the top left of the card.

### For Each Dimension

Interview in this order: **Income → Strategy → Perspiration**

1. Start at 0% confidence
2. Ask probing questions drawn from the framework's Key Questions for that dimension
3. Push for specifics, not generalities
4. Watch for Common Traps listed in the framework and call them out
5. Track confidence as you learn: "I'm at about 40% confidence on Income... that gets me to 75%..."
6. Move on at 90-95% confidence
7. If the user genuinely doesn't know, note low confidence and move on — don't stall

### Red Flags to Watch For

- **Scope creep:** "Well, if we also added X..." — score what's described, not the dream version
- **Validation gaps:** "Customers might want this" — that's a 2 on Income, not a 3
- **Effort optimism:** "It's just a small change" — probe for edge cases, testing, deployment, maintenance
- **Strategy inflation:** "This is really important" — important ≠ differentiating (see Common Traps)
- **User vs. buyer confusion:** The person requesting it may not be the one paying for it

### Proposing Scores

When 90-95% confident on all three dimensions:

```
Based on our conversation:

Income: [score] ([confidence])
  [1-2 sentence reasoning with specific evidence]

Strategy: [score] ([confidence])
  [1-2 sentence reasoning citing competitive position]

Perspiration: [score] ([confidence])
  [1-2 sentence reasoning with time/complexity estimate]

SHIP Score: [I] + [S] - [P] = [total]

[1 sentence overall interpretation referencing the framework's score ranges]

Sound right, or would you adjust anything?
```

### What to Capture in Reasoning

- The core problem this solves
- Who is affected (buyers vs. users, segments, volume)
- Specific evidence cited during the interview (customer names, ticket counts, revenue figures, quotes)
- Open questions or low-confidence areas
- Dependencies on other work
- Any related or potentially duplicate features mentioned

## Batch Scoring

If the user wants to score multiple features in a session:

1. Score one at a time, fully, before moving to the next
2. After each score, ask: "Score another, or review what we have so far?"
3. If reviewing, display a summary table:

```
| Feature                  | I | S | P | SHIP | Confidence |
|--------------------------|---|---|---|------|------------|
| Feature A                | 4 | 3 | 2 |   5  | High       |
| Feature B                | 2 | 2 | 4 |   0  | Medium     |
| Feature C                | 5 | 4 | 3 |   6  | High       |
```

Sort by SHIP score descending. Flag any scores with low confidence.

## Storage

This skill is **storage-agnostic**. It does not assume any particular issue tracker, database, or project management tool.

If the user has a backlog file, spreadsheet, or issue tracker integrated into the project, use it. Otherwise, conduct the interview and present scores in the conversation. The user can record scores however they prefer.

If the user asks you to save or persist scores, ask where they'd like them stored (markdown file, CSV, JSON, etc.) and write accordingly.
