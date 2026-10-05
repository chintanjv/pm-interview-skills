---
name: "pm-metrics-interview"
description: "Answer, score, or mock a PM analytical / metrics / execution interview question (measure success, north star, set a goal, metric dropped, A up B down, should we ship) using the STARTS framework."
---

# Analytical & Metrics Interview: STARTS

Use this skill when the user gives a PM analytical, metrics, or execution interview question and wants a model answer, wants their own answer scored, or wants a live mock. Examples: "How would you measure success for Spotify?", "You're a PM at Meta. Set a goal for Instagram Reels.", "MAU is down 8% this month, what do you do?", "Reels watch time +20% but posts −20%", "Should we remove the profile-photo step from onboarding?", "Improve Meta's payments platform and pick a north star."

The framework was built from *Cracking the PM Interview* (McDowell & Bavaro: metric types, isolate → diagnose → solve, "let company goals decide"), *Decode and Conquer* (Lewis Lin: AARM checklist, Three Loops, decide A/B trade-offs by the strategic goal), 155 top-voted 2023–26 Exponent answers across 40 analytical questions, and Ben Erez's "The definitive guide to mastering analytical thinking interviews" (Lenny's Newsletter, Jul 2025) with his worked Reels and DoorDash templates (assumptions → product rationale → ecosystem metrics → NSM + guardrails → team goal → trade-off).

Core finding: top answers share one spine. What separates them is (1) a product rationale that ends in a one-line product mission and a one-sentence definition of success before any metric, (2) an ecosystem view: every player's "what's in it for me", key actions, and health metrics with timeframes, (3) ONE north star that is a total volume of the value action per period (never an average or ratio), queryable by a data scientist, with the runner-up rejected out loud, (4) an explicit critique of that north star whose drawbacks map one-to-one to guardrails, (5) an "altitude shift" to a team goal prioritized by ability to influence × impact, and (6) trade-off decisions anchored on the shared mission, with what would change your mind.

## Mode selection
- **Answer mode (default):** the user gives a question → produce a complete, interview-ready answer using STARTS.
- **Score mode:** the user pastes their answer or transcript → score it with the 12-point check at the bottom, give the 3 highest-leverage fixes, and rewrite the weakest step.
- **Mock mode:** the user says "mock", "quiz me", or "interview me" → play the interviewer. Give the prompt only, answer clarifying questions briefly, hold back data until asked (for diagnosis cases, invent a consistent hidden root cause and reveal numbers only when the candidate asks the right question). Ask 1–2 realistic follow-ups along a chain: success / north star → "what goal would your team own for the next 6 months?" → a trade-off ("an experiment raised the NSM but cut average order value; roll it out?" or "should Reels replace Stories at the top of the app?") → optionally "your NSM dropped 8%". Then score with the 12-point check.
- **Route out:** if the question is really product design ("design X for Y"), estimation ("how many elevators"), pricing, SQL, or pure market-entry strategy, say so in one line and use a better-suited structure (use the product-sense-interview skill for design prompts). For estimation, still borrow Scope and a closing sanity check. Note: per Erez (2025), root-cause and estimation prompts are becoming less common in analytical-thinking rounds, while Meta execution rounds still use root-cause; weight practice toward success → goal → trade-off chains.

## Step 0: classify the prompt (silently) and pick the R branch
| Trigger words | Branch |
| --- | --- |
| "measure success", "key metrics", "north star" | R1 · Rank |
| "set a goal", "what goals would you set", "what would your team focus on" | R1 · Rank, then R1+ · Set a team goal |
| "dropped", "is down", "declined", "investigate" | R2 · Root-cause |
| "A is up but B is down", "X or Y?", "should Reels replace Stories at the top?" | R3 · Resolve |
| "should we", "would you ship", "decide whether", "invest or kill" | R4 · Run a test |
| "why would X build / keep investing", "improve X and pick a north star" | Hybrid: rationale (or a mini product-sense pass) in A, then R1 |

If the prompt names a real company or product, quickly check current facts (web search) when available so the answer's context isn't stale; state uncertain facts as assumptions.

## Answer mode: STARTS (≈25 min spoken + ≈10 min for the follow-up)

A 45-minute analytical round leaves about 35 minutes of working time, so act as your own time cop. Format: a heading per step with a time budget (e.g., `**R · Rank the North Star (~4 min)**`). Write the lines the candidate would actually say in quotes. Use bullets, small tables, and a code block for metric formulas. Keep prose minimal; be decisive. Before each step, say "let me take a minute to gather my thoughts", then check in at the end of the step before moving on.

### S · Scope & game plan (~1–2 min)
- State 2–4 assumptions that narrow scope without closing off the solution space. Check five flavors: **role** (whose PM hat am I wearing), **markets** (global or a region), **functionality** (what exactly the product does / which surface), **platforms** (mobile, desktop, web), **timing** (current state or at launch). For marketplaces, name every side up front.
- For any named metric: its exact definition, how it's computed, magnitude, window, and comparison baseline.
- Ask only questions whose answers change the approach; state the rest as assumptions with a reason.
- Give the game plan in 30–45 seconds, then ask for buy-in: "I'll start with the product's landscape and reason for existing, then the ecosystem players and their health metrics, then a north star with guardrails, and finally a goal a team could own for the next 3–6 months. Happy to discuss trade-offs at any point. Does that sound like a good plan?"

### T · Target: product rationale (~3–5 min)
Cover three layers, then two anchor lines:
1. **Product context:** what it does, maturity stage (new / growth / mature / bundled), business model and specific revenue streams, the core problem it solves and why it matters now.
2. **Market positioning:** key competitors and the company's unique advantage (graph, data, distribution, ecosystem); one relevant trend.
3. **Company and product alignment:** the company mission → how this product serves it.
- **Product mission statement (mandatory):** one line, e.g., "Empower creators and viewers to meaningfully connect through creative short-form videos." This is the anchor for trade-off decisions later.
- **Definition of success (mandatory):** one sentence ("Events is a coordination tool, so success is people actually showing up, not events created").
- Say what the stage implies (new → adoption/activation; growth → engagement/retention, supply; mature → quality, efficiency, monetization, share of time; bundled → contribution to the parent product).

### A · Actors & actions: ecosystem map (~5–8 min)
- Build the ecosystem table for every player, including the company itself (and advertisers or partners where relevant):

  | Player | Value prop ("what's in it for me?") | Key actions to realize it | Ecosystem health metrics with timeframe |
  | --- | --- | --- | --- |

  Use AARM/AARRR (acquisition, activation, retention, referral, monetization) as a silent checklist so no stage is missed. List only must-have actions, not nice-to-haves. Give 3–5 health metrics per player, each queryable ("# users who stream ≥ 10 min per day/week/month", "# creators who post ≥ 1 Reel per week"). Track daily/weekly/monthly (DWM) here before fixing one timeframe for the north star. Revenue belongs in the company row but is usually not the top-line ecosystem health metric.
- Walk the priority player's journey to the value moment as an arrow chain.
- For metric-change prompts, instead write the metric as a formula and its driver tree (DAU = new + retained + resurrected; revenue = users × conversion × order value; profit = revenue − fixed − variable cost).
- Hybrid "improve" prompts: list 4–5 pain points along the journey, then 3–4 improvement ideas in an impact/effort table, pick ONE with a "because", and define a small MVP.

### R · Core move (~8–12 min) — use the branch playbook below

### T · Trade-offs & guardrails (~3 min)
- Turn each north-star drawback into a guardrail, one-to-one, and state its direction: "should stay above (or below) a healthy baseline". Typical drawbacks → guardrails: quality degradation → completion rate or % orders with complaints; growth from a few heavy users → penetration (% of WAU who engage); acquisition masking churn → 4-week retention per side; unprofitable growth → margin per order or cost per transaction; cannibalization → net platform time; fatigue → notification disable rate; fraud → loss in bps.
- Guardrails can and should be ratios or rates; the north star should not be.
- Data caveats: proxies for offline actions, network effects breaking user-level A/B tests (randomize by cluster, business, or geo), novelty effects.
- Never use generic guardrails alone ("crash rate").

### S · Summarize (~1 min)
A quoted 20–30 second close: mission → north star (or root cause, or decision) → top drivers → top guardrail → team goal or next step → "what would change my mind is…".

## Branch playbooks

### R1 · Rank (define success, ~4 min)
1. From the ecosystem table, find the unifying action that creates value for every player (listening, delivering, watching, transacting).
2. Pick ONE north star passing six checks:
   - reflects value creation across all players;
   - is a **total volume of that action per period** that can grow indefinitely as the ecosystem grows — **never an average or a ratio** (a ratio can rise while the ecosystem shrinks, a false positive);
   - has a timeframe matched to real usage (weekly if people use it several days a week but not daily);
   - is defined precisely enough that a data scientist could query it tomorrow (or measured through a named proxy, e.g., RSVP + check-ins for offline attendance);
   - is hard to game (add a quality bar: "completed", "rated 4+", "≥ 10 minutes", "not refunded within 30 days", "counts only when the task completes");
   - moves within weeks when the team ships.
3. Phrase it: "Total [value actions] per week [meeting a quality bar]." Name the runner-up(s) and why rejected (TPV/GMV skewed by ticket size and promos; CTR gameable; averages and ratios can mislead; lifetime totals are vanity).
4. Critique it in a small table: **strengths** (how it serves each player) and **2–3 drawbacks** (how NSM growth could damage ecosystem health). The drawbacks feed the guardrails in the T step.
5. Break it into 2–3 drivers in a formula code block: breadth × depth × frequency, or funnel conversions.
6. Add one business-link metric where relevant (e.g., advertiser ROAS, renewal rate of users vs matched non-users).

### R1+ · Set a team goal: the "altitude shift" (~5 min)
Use when the prompt asks for goals, or offer it after R1 if time allows. Move from product-level metrics to what one team could own for the next 3–6 months.
1. **Pick the ecosystem player** whose growth unlocks the most NSM growth at the product's current maturity, with a "because" (e.g., creators for Reels because content supply limits watch time; customers for a scaled marketplace because they start every transaction).
2. **Walk that player's journey backward from the NSM event**; the steps before it are candidate leading metrics.
3. **List 3 candidate team goals** as precise metrics (e.g., "% of first-time creators who publish a second Reel within 14 days", "% of carts that become completed orders").
4. **Score them in a table on Ability to influence × Impact on NSM** (High / Medium / Low, each with a one-line reason). Influence includes internal friction: depending on a team you don't own (e.g., the feed ranking team) lowers it.
5. **Prioritize one** with rationale, set it as a goal (metric, baseline → target, timeframe; use a relative target like "+10% in 6 months" when the baseline is unknown), and name 2–3 initiatives that would move it.

### R2 · Root-cause (a metric changed)
1. Pin the metric: definition, computation, magnitude, window, baseline (WoW / MoM / YoY), sudden vs gradual, has it happened before.
2. Rule out data: instrumentation/logging, pipeline, definition change, bot filtering, calendar artifacts (Feb has fewer days; calendar vs rolling MAU).
3. Localize: platform and app version, geo, new vs returning, traffic source, surface/feature, user tier; check sibling products.
4. Decompose into the formula's parts; find which part moved.
5. Hypothesize in four buckets — internal (launch, bug, ranking/notification change, pricing, marketing cut), external (competitor, seasonality, PR, regulation, OS/app-store change, macro), ecosystem (other marketplace side, partners), data. Use the shape: sudden + uniform → release/outage/tracking; gradual → behavior or competition; one segment → something specific to it.
6. Rank 2–3 hypotheses by likelihood × impact (optionally with confidence %), each with the data that would confirm or kill it.
7. Confirm → fix or roll back → size impact → prevent (alert/guardrail).
Say WHY each clarifying question matters. In case-style prompts with hidden data (e.g., a gross-profit drop), ask for specific numbers and follow the tree.

### R3 · Resolve (A up, B down, or option X vs Y) (~10 min)
Two flavors: a **metric conflict** (an experiment raised the NSM but hurt a guardrail; Reels watch time up, posts down) and an **option choice** (Reels or Stories at the top of the app). Open with: "I'd like to clarify the trade-off, then walk you through how I'd navigate the decision."
1. **Clarify the trade-off** in one sentence: what is being decided, and which metric is the NSM vs a guardrail. Check the direction: is each move good or bad? ("Response time down" may be good.)
2. **Metric conflicts only:** check it's real and linked (data sanity, same window, experiment vs organic), then find the mechanism: same users shifting (cannibalization) or different users? Segment.
3. **Common goal:** how both options or metrics serve the product mission statement from the T step.
4. **Frame it:** a pros/cons table for each option, including the status quo.
5. **Name the fundamental trade-off in one line** ("transaction volume vs transaction value", "social connection vs entertainment discovery").
6. **Find the tiebreaker** metric both roll up to (total $ spent in the test group, total time spent, positions filled, retention) and judge the net effect, short- and long-term, across every ecosystem player.
7. **Decide** by which option best serves the mission and the company's current goal; propose a mitigation for the losing side; finish with 2–3 conditions under which you would reverse ("I'd revisit if unit economics turn negative, merchant satisfaction drops, or customer LTV declines").

### R4 · Run a test (ship / change / invest)
1. Hypothesis and goal: "We believe [change] will raise [metric] because [reason]"; ask why it's being considered.
2. Map affected actors and predicted + / − effects on each.
3. State the decision rule BEFORE the test: primary metric, minimum effect worth shipping, guardrails with thresholds.
4. Design: randomization unit (user vs cluster/business/geo for network effects), control vs treatment (add a third arm when useful), segment, sample size, ≥ 1–2 full weekly cycles, novelty watch, long-term holdout.
5. Read: statistical significance (p < 0.05 means a difference this large would appear < 5% of the time if the change had no real effect) plus practical significance and segment differences.
6. Decide ship / iterate / kill. For invest-or-kill: retention curves flattening, cohort improvement, qualitative pull vs cost to continue and opportunity cost; set kill criteria in advance. If results conflict, switch to R3.

## Metric library (starting menu — adapt, don't recite)
| Product type | North star shape (total per period) | Guardrails that show judgment (ratios welcome) |
| --- | --- | --- |
| Social feed | Total meaningful interactions (comments, shares, messages) per week | Net platform time, hide/report rate, notification disables |
| Short video / creator | Total watch time per week | Completion rate, viewed-video duration range, penetration (% of WAU engaging), creator retention |
| Audio / music streaming | Total streaming hours per week | Explicit interactions (likes, saves, playlist adds) per listening hour |
| Two-sided marketplace | Total completed transactions per week with a quality bar (delivered & rated 4+, positions filled) | % orders with complaints, 4-week retention per side, margin per order, fraud |
| Messaging / comms | Total messages sent or meetings completed per week | Latency, failed calls, spam reports as % of messages |
| Productivity SaaS | Weekly active teams doing the core job (count) | Time on sibling apps (bundles), sync errors |
| Subscription media | Total engaged hours per week | Churn/renewal by cohort, cannibalization |
| Payments / fintech | Weekly successful, non-disputed transactions | Fraud loss (bps of TPV), chargebacks, auth failure rate, cost per transaction |
| E-commerce | Total purchases per week (repeat buyers as a driver) | Return rate, delivery time, average order value |
| Ads | Total weekly advertiser conversions or ad revenue (impressions × price), not CTR | Session time and retention vs holdout, ad hides, advertiser ROAS distribution |
| AI assistant / feature | Weekly successful tasks (completed, accepted, not edited away) | Hallucination/grounding failures, safety incidents, p95 latency, cost per successful task |
| Internal platform | Weekly successful production workloads | Incident rate, cost per task, dev satisfaction |
| Customer support | Weekly tickets resolved on first contact with CSAT ≥ 4 | Reopen rate, core-product engagement of ticket filers |

AI products: measure two layers — product outcome (job done, user returns) and model quality (eval pass rate, hallucination, latency, cost).

## Rules for every answer
1. Pause before each section ("let me take a minute"), state the plan once, check in at each transition, then sound conversational — never recite the acronym mechanically.
2. Treat the round as a game with rules: assumptions and game plan first, then follow your own time budget.
3. Measure over a fixed window, never lifetime totals. The north star is a volume per period; averages, ratios, and rates belong in drivers and guardrails.
4. Define every metric so a data scientist could query it: numerator, denominator, window, what counts as "active".
5. One north star, 2–3 drivers, guardrails mapped one-to-one to its drawbacks, 3–5 health metrics per player at most; every choice has a "because" and a rejected alternative.
6. Segment by default (new vs returning, platform, geo, cohort, heavy vs light, each marketplace side).
7. When metrics or options conflict, decide by the product mission and the company's current goal.
8. Always land a recommendation, plus what would change your mind.
9. Where the user's own background is known and relevant (e.g., payments/fintech), weave in domain-specific metrics that signal real experience.

After an answer, add 2–3 lines on **why this answer scores well** (which differentiators it hit), then offer the most likely interviewer follow-up as a practice prompt.

## Score mode: 12-point check
Mark each ✅ / ⚠️ / ❌ with a one-line reason:
1. Stated scoping assumptions (role, markets, functionality, platforms, timing) and a game plan with buy-in.
2. Product rationale covered context (maturity, business model), positioning (competitors, unique advantage), and alignment, ending in a one-line product mission.
3. Defined success in one sentence before naming a metric, and let product stage set the focus.
4. Mapped every ecosystem player with value prop, key actions, and queryable health metrics with timeframes.
5. Committed to ONE north star (or ONE ranked hypothesis / decision rule) with a quality bar.
6. The north star is a total volume with a timeframe, not an average or ratio, and the runner-up was rejected out loud.
7. Critiqued the north star and mapped each drawback to a guardrail with a baseline direction; added a data or experiment caveat.
8. Wrote the metric as a formula / driver tree (or, for diagnosis: validated data → localized → decomposed → read the shape).
9. When goals were asked: made the altitude shift, picked a player with a "because", and prioritized a team goal by ability to influence × impact on the NSM.
10. Trade-offs: named the common goal, compared pros and cons, stated the fundamental trade-off in one line, and decided by the mission; set ship/kill criteria before results for tests.
11. Said what would change their mind.
12. Landed a clear recommendation in a 20–30 s summary; the main answer fit in ≤ 25 min, leaving room for a follow-up.

Then give: an overall readiness verdict (Strong / Borderline / Not yet), the 3 highest-leverage fixes, and a rewritten version of the weakest step. Also flag common failures: laundry lists of 20 metrics, metrics before a goal, an average or ratio as the north star, undefined "active", vanity totals, generic guardrails, skipping the north-star critique, no altitude shift to a team goal, theorizing before checking data, ignoring the other side, forgetting network effects in A/B tests, loose p-value statements, no final recommendation.