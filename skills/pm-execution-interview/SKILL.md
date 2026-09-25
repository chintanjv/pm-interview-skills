---
name: "pm-execution-interview"
description: "Answer, mock or score a PM execution interview question (success metrics, metric drop, A up B down, ship/launch, experiment) using the 6-step C-G-M-A-D-S playbook with modules and overlays."
---

# PM Execution Playbook

A 3-layer framework for product execution / analytical / metrics interview questions, synthesized from Cracking the PM Interview (McDowell & Bavaro), Decode and Conquer (Lewis Lin), and an analysis of the top answers to the 25 most popular Exponent PM execution questions.

Use this skill instead of generic metrics frameworks whenever the user asks an execution-style question, says "use my execution framework / playbook", or asks to answer, mock or score one.

## Modes

Pick the mode from the request. If unclear, default to ANSWER.

1. **ANSWER**: the user gives a question and wants a model answer. Produce the full answer in the output format below.
2. **MOCK**: the user wants to practice. Play the interviewer. Give the question only, answer clarifying questions briefly with realistic data, reveal data only when asked, push with follow-ups along the follow-up chain, then score with the rubric at the end. Never give the model answer until the user finishes or asks.
3. **SCORE**: the user pastes their own answer. Score it against the rubric, quote the strongest and weakest moments, and rewrite the weakest step.
4. **GENERATE**: the user asks for a question. Create a realistic question (ideally a 2-3 part chain on a real product, AI products preferred when relevant), then answer it unless they want to try it first.

## Layer 1: the spine (every question)

Mnemonic: **"Can Good Metrics Actually Drive Success?"** Total target: 25-33 min.

0. **Pause and classify (20-30 sec):** pick the module (A-H) and any overlays. Say "Give me a moment to structure my thoughts."
1. **Clarify (2-3 min):** product and scope (surface, platform, region, segment); exact metric definition, time window, comparison baseline, size of change; for metric changes ask **sudden or gradual**. Max 3-5 questions, each with a reason, then state assumptions.
2. **Goal (2-3 min):** mission -> product goal -> business goal, one line each. State **product stage** (new = adoption, mature = quality/retention/revenue). Name user types / sides. Check in.
3. **Map (4-5 min):** users x journey grid (discover -> act -> value moment -> return), or a **metric tree** for drops and conflicts. Pick the 2-3 personas that matter.
4. **Analyze (12-15 min):** run the module (Layer 2) with any overlays (Layer 3).
5. **Decide (3-4 min):** commit to one North Star / root cause / ship call / lever. Give 2 reasons and what would change your mind. Never end on "it depends".
6. **Safeguard & summarize (2-3 min):** guardrails, risks (privacy, trust & safety, cannibalization, other side of marketplace), validation plan (A/B, holdout, alert), 20-second recap, offer to go deeper.

## Layer 2: modules (step 4, by what is asked)

**A. Success metrics / goals** ("measure success", "set goals", "North Star")
1. Funnel per side: acquisition, activation, engagement, retention, monetization. Cross out stages the question does not touch.
2. One North Star that passes 4 tests: reflects user value delivered, leads to business outcome, team can move it, hard to game. Say why it beats the obvious alternative.
3. 3-4 input metrics, one per key journey step.
4. 2-3 guardrail / counter metrics (quality, spam/abuse, cannibalization of core product, notification fatigue).
5. How you would measure any hard-to-observe metric (proxies, surveys).
6. For "set a goal": baseline -> target -> deadline (e.g. from 18% to 21% in 2 quarters).

**B. Metric drop / root cause**
1. Is it real? Logging, definition change, pipeline; year-over-year for seasonality.
2. Is it bad? Check related metrics (fewer opens but longer sessions can be fine).
3. Scope: sudden vs gradual; segment by region, platform/app version, new vs existing, user type, entry point; check sibling products.
4. Isolate with the metric tree: find the one component that moved.
5. Rank 2-3 hypotheses with rough % confidence across internal (release, ranking, pricing, marketing, outage) and external (competitor, seasonality, macro, OS/app-store) causes. Name the evidence that would confirm each.
6. Root cause -> fix (rollback/mitigate) -> prevent (monitoring, alerts).

**C. Metric conflict / trade-off / ship call** ("X up, Y down", "should we ship", "A or B")
1. Tie both metrics to the goal/North Star; ask which matters most now (company goal decides, per both books).
2. Explain the movement: cannibalization, mix shift, measurement artifact, cohort behavior change.
3. Check total ecosystem (is total time/engagement up?).
4. Stakeholder-by-stakeholder pros and cons, short vs long term.
5. Pre-committed decision rules: primary metric, guardrail thresholds, what means ship / iterate / kill.

**D. Improve a metric**
1. Lever tree (e.g. transactions = sellers x listings per seller x conversion x repeat rate).
2. Pick one lever by impact x control x stage, and one segment.
3. Three solutions, prioritize (impact, effort, confidence), go deep on one.
4. Success metric + one guardrail.

**E. Execution judgment** (team, roadmap, stakeholders)
1. Diagnose the real problem behind the symptom.
2. Set the P0 and check current work against it; do not thrash engineers.
3. Align partners (sales, PMM, customers) -> plan -> measure -> prevent recurrence.

**F. Launch / go-to-market**
1. Product, target user, risks, competitive position.
2. One launch goal (adoption, validate PMF, revenue, protect trust).
3. Launch design: MVP vs full, test market, invite vs open, staged rollout (internal -> 1% -> 10% -> 50% -> 100%).
4. Pre / during / post: readiness, user types, channels, partners.
5. Success metrics plus pre-set kill / rollback criteria.

**G. Experiment design**
1. Hypothesis: changing X moves Y by Z because...
2. Randomization unit: user, or cluster/geo when network effects exist.
3. One primary metric, 2-3 guardrails, minimum effect worth detecting.
4. Duration: at least 1-2 full weekly cycles; novelty/learning effects; long-term holdout.
5. Read-out: sample-ratio check, statistical and practical significance, segment cuts for harmed groups.
6. Decision rules written before launch.

**H. Behavioral execution** (Google Craft & Execution, cross-functional)
1. One-line principle.
2. One real STAR story with a number.
3. The process you would install and what you would do differently.

## Layer 3: overlays (steps 2-4, by product type)

**AI products** (assistants, agents, AI search, copilots)
- Measure task outcome, not clicks. Journey: intent -> prompt -> response -> accept / edit / regenerate / abandon -> task done -> return.
- Metrics: task success rate, acceptance (no-edit) rate, regenerate rate, thumbs ratio, human takeover rate for agents, hallucination / groundedness rate, safety violation rate, p95 latency, cost per task; for AI search, good abandonment and source click-through.
- Offline evals (golden sets, rater side-by-sides) before online A/B; note they can disagree.
- Extra RCA causes: model version, prompt/system-prompt change, retrieval index freshness, provider outage, query-mix shift, rate limits or cost caps.
- Guardrails: trust & safety, privacy, over-reliance on wrong answers.

**B2B / SaaS**
- Map buyer vs admin vs end user across trial -> onboarding -> adoption -> renewal -> expansion.
- Metrics: time to value, account activation, seat utilization (WAU / paid seats), feature depth, NRR / GRR, expansion revenue, logo churn, tickets per account.
- Extra RCA causes: large-account concentration, renewal timing, pipeline slowdown, admin policy or permission changes, integration breakage.

**Marketplace**
- Liquidity (match rate, time to match, fill rate), supply-demand balance, repeat use per side, concentration.
- Always check both sides; a win for one side can hurt the other.

## Reference libraries

**Metric trees**
- DAU = new + retained + resurrected
- Revenue = users x paying % x ARPPU
- Profit = revenue - fixed cost - variable cost
- GMV = buyers x orders per buyer x average order value
- Time spent = sessions x session length
- Transactions = sellers x listings per seller x conversion
- Clicks below a module = queries x trigger rate x scroll-past rate x CTR

**The follow-up chain** interviewers use: measure success (A) -> North Star drops (B) -> fix hurts a guardrail (C) -> test it (G) -> roll it out (F). Keep the same goal and metric tree across the chain.

## Output format (ANSWER and GENERATE modes)

1. Restate the question and label: Module + Overlays + total time budget.
2. One section per spine step, headed with the step name and time estimate (e.g. "1. Clarify (2 min)").
3. Inside each step, write what the candidate would say: short bullets or a numbered list, minimal prose, concrete numbers. Mark all invented data and interviewer replies as illustrative.
4. Use a table for users x journey, hypotheses x evidence, or stakeholder pros/cons when it helps.
5. End with a 20-second recap in quotes.
6. Close with a "Why this scores well" checklist mapping to the 7 habits below, plus 1-2 likely follow-up questions.

## Scoring rubric (MOCK and SCORE modes)

Score each habit 0-2 (total /14), then give the top fix:
1. Defined the metric/feature precisely before analyzing.
2. Let goal and product stage drive metric choice.
3. Drew a map (users x journey) or metric tree.
4. Ranked hypotheses / picked one North Star instead of listing.
5. Asked "is this change even bad?" when relevant.
6. Set decision rules or guardrails before judging results.
7. Committed to a clear decision and recapped, within ~33 min.

Also flag: more than 5 clarifying questions, reciting the framework robotically, solutions without prioritization, no numbers.

## Delivery rules to coach

- Signpost the plan in one natural sentence, not a numbered list of steps.
- Check in after Goal and after hypotheses / metric list.
- Structure on the whiteboard as you go.
- Use numbers, even rough ones.
- If the interviewer answers a question with "what do you think?", stop asking and decide.