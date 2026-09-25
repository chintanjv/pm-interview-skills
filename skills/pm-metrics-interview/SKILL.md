---
name: "pm-metrics-interview"
description: "Answer, score, or mock a PM analytical / metrics / execution interview question (measure success, north star, metric dropped, A up B down, should we ship) using the STARTS framework."
---

# Analytical & Metrics Interview: STARTS

Use this skill when the user gives a PM analytical, metrics, or execution interview question and wants a model answer, wants their own answer scored, or wants a live mock. Examples: "How would you measure success for Facebook Events?", "MAU is down 8% this month, what do you do?", "Reels watch time +20% but posts −20%", "Should we remove the profile-photo step from onboarding?", "Improve Meta's payments platform and pick a north star."

The framework was built from *Cracking the PM Interview* (McDowell & Bavaro: metric types, isolate → diagnose → solve, "let company goals decide"), *Decode and Conquer* (Lewis Lin: AARM checklist, Three Loops, decide A/B trade-offs by the strategic goal), and 155 top-voted 2023–26 Exponent answers across 40 analytical questions. Core finding: top answers share one spine. What separates them is (1) a one-sentence definition of success before any metric, (2) ONE primary metric with a quality bar and the runner-up rejected out loud, (3) the metric written as a formula and broken into drivers, (4) guardrails specific to that north star (cannibalization, fatigue, quality, the other side of the marketplace), and (5) a clear recommendation.

## Mode selection
- **Answer mode (default):** the user gives a question → produce a complete, interview-ready answer using STARTS.
- **Score mode:** the user pastes their answer or transcript → score it with the 10-point check at the bottom, give the 3 highest-leverage fixes, and rewrite the weakest step.
- **Mock mode:** the user says "mock", "quiz me", or "interview me" → play the interviewer. Give the prompt only, answer clarifying questions briefly, hold back data until asked (for diagnosis cases, invent a consistent hidden root cause and reveal numbers only when the candidate asks the right question), ask 1–2 realistic follow-ups (e.g., success → "your north star dropped 8%" → "A up, B down, do you ship?"), then score with the 10-point check.
- **Route out:** if the question is really product design ("design X for Y"), estimation ("how many elevators"), pricing, SQL, or pure market-entry strategy, say so in one line and use a better-suited structure (use the product-sense-interview skill for design prompts). For estimation, still borrow Scope and a closing sanity check.

## Step 0: classify the prompt (silently) and pick the R branch
| Trigger words | Branch |
| --- | --- |
| "measure success", "key metrics", "north star", "what goals would you set" | R1 · Rank |
| "dropped", "is down", "declined", "investigate" | R2 · Root-cause |
| "A is up but B is down", "what would you do" | R3 · Resolve |
| "should we", "would you ship", "decide whether", "invest or kill" | R4 · Run a test |
| "why would X build / keep investing", "improve X and pick a north star" | Hybrid: rationale (or a mini product-sense pass) in A, then R1 |

If the prompt names a real company or product, quickly check current facts (web search) when available so the answer's context isn't stale; state uncertain facts as assumptions.

## Answer mode: STARTS (≈25 min spoken)

Format: a heading per step with a time budget (e.g., `**R · Rank the North Star (~8 min)**`). Write the lines the candidate would actually say in quotes. Use bullets, small tables, and a code block for metric formulas. Keep prose minimal; be decisive.

### S · Scope (1–2 min)
- Confirm product surface, users, platform/geo, product stage (new / growth / mature / bundled), and for any named metric: its exact definition, how it's computed, magnitude, time window, and comparison baseline.
- Ask only 2–4 questions whose answers change the approach; state the rest as assumptions with a reason. End with "Is that framing OK?"

### T · Target (2–3 min)
- Company mission and business model in one line each, then why this product exists for the company.
- **Mandatory:** one sentence defining success ("Events is a coordination tool, so success is people actually showing up, not events created").
- Say what the stage implies (new → adoption/activation; growth → engagement/retention; mature → quality, efficiency, monetization, share of time; bundled → contribution to the parent product).

### A · Actors & actions (3–4 min)
- List every actor, including every side of a marketplace and internal/partner actors where relevant; pick the priority one with a "because".
- Walk the journey to the value moment as an arrow chain.
- For metric-change prompts, instead write the metric as a formula and its driver tree (DAU = new + retained + resurrected; revenue = users × conversion × order value; profit = revenue − fixed − variable cost).
- Hybrid "improve" prompts: list 4–5 pain points along the journey, then 3–4 improvement ideas in an impact/effort table, pick ONE with a "because", and define a small MVP.

### R · Core move (10–15 min) — use the branch playbook below

### T · Trade-offs & guardrails (3–4 min)
- 2–3 counter-metrics tied to THIS north star: cannibalization of other surfaces (net platform time), quality/spam, notification fatigue, gaming, the other marketplace side, short- vs long-term, fraud/cost where money moves.
- Data caveats: proxies for offline actions, network effects breaking user-level A/B tests (randomize by cluster, business, or geo), novelty effects.
- Never use generic guardrails alone ("crash rate").

### S · Summarize (1–2 min)
A quoted 20–30 second close: goal → north star (or root cause, or decision) → top drivers → top guardrail → next step → "what would change my mind is…".

## Branch playbooks

### R1 · Rank (define success)
1. Brainstorm per journey stage and per side with AARM/AARRR as a silent checklist; say 5–6 candidates, not 20.
2. Pick ONE north star passing four checks: captures user AND business value (all sides); moves within weeks (actionable); hard to game (quality bar: "rated 4+", "watched 30%+", "not refunded within 30 days", "counts only when the task completes"); measurable now or via a named proxy.
3. Phrase it: "Weekly [units] that [complete the value action] [meeting a quality bar]." Name the runner-up(s) and why rejected (e.g., GMV/TPV skewed by ticket size and promos; CTR gameable; totals are vanity).
4. Break it into 2–3 drivers in a formula code block: breadth × depth × frequency, or funnel conversions.
5. Add one business-link metric where relevant (e.g., advertiser ROAS lift, renewal rate of users vs matched non-users).

### R2 · Root-cause (a metric changed)
1. Pin the metric: definition, computation, magnitude, window, baseline (WoW / MoM / YoY), sudden vs gradual, has it happened before.
2. Rule out data: instrumentation/logging, pipeline, definition change, bot filtering, calendar artifacts (Feb has fewer days; calendar vs rolling MAU).
3. Localize: platform and app version, geo, new vs returning, traffic source, surface/feature, user tier; check sibling products.
4. Decompose into the formula's parts; find which part moved.
5. Hypothesize in four buckets — internal (launch, bug, ranking/notification change, pricing, marketing cut), external (competitor, seasonality, PR, regulation, OS/app-store change, macro), ecosystem (other marketplace side, partners), data. Use the shape: sudden + uniform → release/outage/tracking; gradual → behavior or competition; one segment → something specific to it.
6. Rank 2–3 hypotheses by likelihood × impact (optionally with confidence %), each with the data that would confirm or kill it.
7. Confirm → fix or roll back → size impact → prevent (alert/guardrail).
Say WHY each clarifying question matters. In case-style prompts with hidden data (e.g., a gross-profit drop), ask for specific numbers and follow the tree.

### R3 · Resolve (A up, B down)
1. Check the direction: is each move good or bad? ("response time down" may be good.) State your reading.
2. Check it's real and linked (data sanity, same window, experiment vs organic).
3. Find the mechanism: same users shifting (cannibalization) vs different users; segment.
4. Find the tiebreaker metric both roll up to (total time spent, positions filled, retention, revenue per user) and judge the net effect.
5. Weigh ecosystem and long run (fewer posts today → less inventory tomorrow).
6. Decide by the company's current goal, then propose a mitigation for the losing side.

### R4 · Run a test (ship / change / invest)
1. Hypothesis and goal: "We believe [change] will raise [metric] because [reason]"; ask why it's being considered.
2. Map affected actors and predicted + / − effects on each.
3. State the decision rule BEFORE the test: primary metric, minimum effect worth shipping, guardrails with thresholds.
4. Design: randomization unit (user vs cluster/business/geo for network effects), control vs treatment (add a third arm when useful), segment, sample size, ≥ 1–2 full weekly cycles, novelty watch, long-term holdout.
5. Read: statistical significance (p < 0.05 means a difference this large would appear < 5% of the time if the change had no real effect) plus practical significance and segment differences.
6. Decide ship / iterate / kill. For invest-or-kill: retention curves flattening, cohort improvement, qualitative pull vs cost to continue and opportunity cost; set kill criteria in advance.

## Metric library (starting menu — adapt, don't recite)
| Product type | North star shape | Guardrails that show judgment |
| --- | --- | --- |
| Social feed | Daily users with a meaningful interaction | Net platform time, hide/report rate, notification disables |
| Short video / creator | Watch time per DAU with a completion floor | Content diversity, time taken from other surfaces, creator retention |
| Two-sided marketplace | Successful transactions with a quality bar (delivered & rated 4+, positions filled, GMV) | Cancellations, complaints, supply-side churn, fraud |
| Messaging / comms | Daily users sending; meetings completed | Latency, failed calls, spam reports |
| Productivity SaaS | Weekly active teams doing the core job | Time on sibling apps (bundles), sync errors |
| Subscription media | Weekly engaged subscribers; hours per subscriber | Churn/renewal by cohort, cannibalization |
| Payments / fintech | Weekly successful, non-disputed transactions; revenue or gross profit per active | Fraud loss (bps of TPV), chargebacks, auth failures, cost per transaction |
| E-commerce | Purchases from repeat buyers; revenue per visitor | Returns, delivery time |
| Ads | Ad revenue per user (impressions × price), not CTR alone | Session time and retention vs holdout, ad hides |
| AI assistant / feature | Weekly successful tasks (completed, accepted, not edited away) | Hallucination/grounding failures, safety incidents, p95 latency, cost per successful task |
| Internal platform | Weekly successful production workloads | Incident rate, cost per task, dev satisfaction |
| Customer support | CSAT + first-contact resolution | Reopen rate, core-product engagement of ticket filers |

AI products: measure two layers — product outcome (job done, user returns) and model quality (eval pass rate, hallucination, latency, cost).

## Rules for every answer
1. Think 30–60 s, state the plan once, then sound conversational — never recite the acronym mechanically.
2. Check in after Target and after the core move, not after every sentence.
3. Prefer rates and ratios to totals; measure change, not lifetime volume.
4. Define every metric: numerator, denominator, window, what counts as "active".
5. One primary, 2–3 drivers, 2–3 guardrails; every choice has a "because" and a rejected alternative.
6. Segment by default (new vs returning, platform, geo, cohort, heavy vs light, each marketplace side).
7. When metrics conflict, decide by the company's current goal.
8. Always land a recommendation, plus what would change your mind.
9. Where the user's own background is known and relevant (e.g., payments/fintech), weave in domain-specific metrics that signal real experience.

After an answer, add 2–3 lines on **why this answer scores well** (which differentiators it hit), then offer the most likely interviewer follow-up as a practice prompt.

## Score mode: 10-point check
Mark each ✅ / ⚠️ / ❌ with a one-line reason:
1. Announced a structure and scoped with only questions that change the approach.
2. Defined success in one sentence before naming a metric.
3. Let product stage set the focus.
4. Covered every actor / marketplace side.
5. Committed to ONE primary metric (or ONE ranked hypothesis / decision rule) with a quality bar and definition.
6. Rejected a runner-up out loud with a reason.
7. Wrote the metric as a formula / driver tree (or, for diagnosis: validated data → localized → decomposed → read the shape).
8. Guardrails specific to the north star, plus a data or experiment caveat.
9. Decided by the company's goal where metrics conflict; set ship/kill criteria before results for tests.
10. Landed a clear recommendation in a 20–30 s summary; fits in ≤ 30 min spoken.

Then give: an overall readiness verdict (Strong / Borderline / Not yet), the 3 highest-leverage fixes, and a rewritten version of the weakest step. Also flag common failures: laundry lists of 20 metrics, metrics before a goal, undefined "active", vanity totals, generic guardrails, theorizing before checking data, ignoring the other side, forgetting network effects in A/B tests, loose p-value statements, no final recommendation.