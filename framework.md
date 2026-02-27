<!-- Version: 2026-02-27 -->
# SHIP Scoring Framework

**Formula:** `SHIP Score = Income + Strategy - Effort`

**Score range:** -3 (worst) to +11 (best)

---

## Income (1-5): Risk-Adjusted Revenue Impact

Measures **willingness to pay** and **revenue risk**. Certainty adjusts score downward.

**Key question:** How confident are you that buyers would pay us a lot more for this, or leave without it?

| Score | Definition |
|-------|------------|
| **5** | **Revenue committed or at immediate risk** — multiple customers require this to renew (active churn risk), fixes a broken payment/billing process that is measurably leading to lost revenue, addresses compliance/resiliency requirement threatening existing revenue, fixes critical bug causing measurable churn, prospect committed to sign if built (sale-contingent), agreed during sales/onboarding as part of closing |
| **4** | **High-confidence revenue with existing validation** — existing customers explicitly requested AND committed to paying, directly enables validated upsell/expansion opportunity |
| **3** | **Probable revenue with some validation** — customers expressed willingness to pay but haven't committed, fits proven buyer categories but specific demand untested, maintains table stakes to prevent future churn, technical debt/maintenance preventing imminent issues |
| **2** | **Possible revenue with limited validation** — assumed valuable but no direct customer validation, may help sales conversations but not a blocker, general improvements with unclear revenue connection, preventive maintenance with no immediate risk |
| **1** | **Speculative or minimal revenue impact** — no clear relationship to revenue, internal tools with indirect impact, "nice to have" from non-paying users/prospects |

### Key Questions

- Would a buyer pay more for this, or leave without it?
- Who is asking — buyers (budget holders) or users (no purchasing power)?
- Are the people who want this actually willing to pay us for this?
- How certain are we? (Uncertainty adjusts score downward)
- Is this a churn risk or lost sale factor?

### Common Traps

- **User requests ≠ buyer demand** — users are not always the ones with purchasing power
- **Request count ≠ revenue impact** — consider which users/buyers are asking for it; if it is being requested by low-paying customers or non-paying users, cannot weight as highly as requests from high-paying customers
- **"Nice to have" without pain (pain should be evinced by a current manual process, workarounds, or clear frustration)** = highly speculative (score 1)

---

## Strategy (1-5): Competitive Differentiation

Measures **competitive advantage** and **differentiation in ways customers care about**.

| Score | Definition |
|-------|------------|
| **5** | **Market-defining** — creates unique capability competitors can't easily match, opens new market segments, builds moats (network effects, data advantage, switching costs), defines your product's core identity. RARE |
| **4** | **Significant** —meaningfully strengthens existing competitive advantage, makes you the obvious choice for a use case, increases switching costs meaningfully |
| **3** | **Notable** — notably better than alternatives in ways customers value, somewhat strengthens existing competitive advantage |
| **2** | **Incremental** — matches competitor features (table stakes), marginal improvement over status quo, nice differentiator but not decision-driver, improves experience but not uniquely |
| **1** | **None** — every competitor has this, customers don't factor this into decisions, pure technical improvements invisible to customers even if internal value |

### Key Questions

- Could competitors easily copy this? What resources, time, connections, etc would it take for competitors to copy?
- Would this be a decision-driver for buyers?
- Is this a "checkbox feature" or a real advantage?
- Does this open new market segments?
- Does this build on existing advantages?
- Would this make us the only option for some buyers?

### Common Traps

- **Most features are Strategy 2-4** (Strategy 5 is rare)
- **"Important" ≠ "differentiating"**
- Just because a competitor has a feature, does not mean you need to copy it
- Your competitive advantages may be largely invisible to customers
- Consider jobs-to-be-done; competitors are also people doing things themselves (building own solutions), manually, or choosing not to do something (inertia)
- consider Porter’s 4 basic strategies (Cost Leadership, Differentiation, Cost Focus, Differentiation Focus): your competitive strategy should be consistent across tasks and projects. You cannot choose a cost focus-informed approach for one project and a differentiation approach for another
- consider customer segments and ICPs; competitive advantages for one customer segment may be different for another segment
- **"Strategic foundation" ≠ customer-facing differentiation**
- **Table stakes features** are usually Strategy 1-2, not higher

---

## Perspiration (Engineering, Operationalizing, and Maintenance Effort): 1-5

Measures **engineering time and complexity**. Complexity should include the amount of QA involved as well as maintenance burden. Cycles assume 2 week cycles.

| Score | Definition |
|-------|------------|
| **1** | **Quick win** — well-understood, minimal risk, clear implementation path. |
| **2** | **Small project** — Mostly known technology, limited dependencies, contained scope. Can be deployed in one cycle. |
| **3** | **Medium project** — Some technical unknowns, cross-system changes, requires careful planning but can be deployed in 2 cycles. |
| **4** | **Large project** — Significant unknowns or new technology, major architectural changes, 2-3 cycles. |
| **5** | **Very large** — High technical risk, requires research/prototyping, 4+ cycles, blocks other development. |

### Key Questions

- What's your gut on build time?
- Any technical unknowns or dependencies?
- Has this been estimated before?
- What's the complexity beyond the happy path?
- Are there integration/testing/deployment complications?
- What else could we be working on the time we will spend scoping, building, and QAing this?
- Will this block/unblock other work?
- Do we have the skills, resources, and time to maintain this going forward?


### Common Traps

- **Optimism bias is real** — add buffer if uncertain
- **Unknown technical complexity** = medium confidence at best
- **"Just a UI change"** often has backend implications
- New features may also require UX or UI changes, add uncertainty for tasks requiring conceptual work
- **Don't forget testing, edge cases, interconnections, deployment, maintenance**

---

## Confidence Levels

Each score (Income, Strategy, Effort) has an associated confidence level:

- **high** — Strong evidence, clear data, minimal uncertainty
- **medium** — Some evidence, reasonable assumptions, moderate uncertainty
- **low** — Weak evidence, significant assumptions, high uncertainty

### When Confidence is Low

| Low confidence in... | Indicates... | Action needed |
|---------------------|--------------|---------------|
| **Income** | Demand unclear | Validate with customers, search support tickets, sales call notes/transcripts |
| **Strategy** | Differentiation unclear | Competitor research, customer interviews |
| **Effort** | Build complexity unclear | Technical spike with devs, architecture review |

---

## Common Scenarios

| Scenario | I | S | E | SHIP | Notes |
|----------|---|---|---|------|-------|
| Enterprise Request | 4 | 2 | 3 | **3** | Big customer wants specific feature. High income confidence, some differentiation, medium complexity. Probably worth doing. |
| Technical Debt Paydown | 1 | 1 | 5 | **-3** | Large refactor with indirect benefits. Low revenue impact, no differentiation, high effort. Break into smaller pieces with revenue impact. |
| Quick Fix | 1 | 1 | 1 | **1** | Small customer annoyance. Some retention value, minimal differentiation, easy fix. Do when convenient. |
| Platform Play | 4 | 5 | 5 | **4** | Major capability opening new markets. Good revenue potential, huge differentiation, massive effort. Worth the big bet. |
| Competitor Copy | 3 | 1 | 2 | **2** | Feature competitors have that customers expect. Revenue protection, low differentiation, modest effort. Important but uninspiring. |


## Interpreting SHIP Scores

After scoring, features fall into rough categories:

| SHIP Score | Interpretation | Action |
|-----------|---------------|---------|
| **6+** | Excellent — high impact, clear win | Prioritize |
| **3-5** | Good — solid features worth building | Candidate |
| **0-2** | Medium — questionable ROI | Revisit when context changes |
| **Negative** | Low — poor ROI, avoid | Park or defer indefinitely |

**Note:** These are guidelines, not hard rules. Context matters. A score of 2 with very high confidence might be better than a 5 with low confidence.

---

## Scoring Philosophy

- **Evidence over intuition** — push for specific examples
- **Confidence matters** — 90%+ confidence is the goal
- **Be honest about uncertainty** — low confidence scores are valuable signals
- **Revisit as context changes** — scores are not permanent
