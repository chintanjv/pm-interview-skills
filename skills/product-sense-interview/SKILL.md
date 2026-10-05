---
name: "product-sense-interview"
description: "Answer a PM product design / product sense interview question (design X, improve X, favorite product) using the 8-step CIRCLES+M framework, or score a practice answer."
---

# Product Sense Interview: CIRCLES+M

Use this skill when the user gives a product design / product sense interview question (e.g., "You're a PM at Meta. Design a product for group travel", "Improve Spotify", "Design a fire alarm for the deaf", "What's your favorite product?") and wants a model answer, OR asks to have their own answer scored.

The framework was built from *Cracking the PM Interview* (McDowell & Bavaro), *Decode and Conquer* (Lewis Lin, CIRCLES), an analysis of 112 top-voted 2023–26 Exponent answers across 25 questions, and Ben Erez's "Definitive guide to mastering product sense interviews" (Lenny's Newsletter, 2025; ex-Meta interviewer). Core findings:
- Top answers use the same spine as everyone else. What separates them is (1) a one-line reframe of the real problem, (2) explicit prioritization with named criteria and a "because", (3) committing to ONE solution with a concrete v1, and (4) metrics with guardrails plus risks.
- Clarifying questions and reciting the company mission are table stakes; they do not differentiate on their own.
- Interviewers score each dimension separately (communication, product motivation, segmentation, problem identification, solution development). You must pass every one; excellence in one cannot compensate for weakness in another. The bar is the same across seniority levels.

## Mode selection
- **Answer mode (default):** the user gives a question → produce a complete, interview-ready answer following the 8 steps below.
- **Score mode:** the user pastes their own answer or transcript → score it with the rubric and 10-point check at the bottom, give the 3 highest-leverage fixes, and rewrite the weakest step.
- If the question is actually metric diagnosis ("DAU dropped 10%"), estimation, pure strategy ("should X enter Y"), or an execution trade-off, say so in one line and use a better-suited structure instead of forcing this framework.

## Answer mode: the 8 steps (≈33 min spoken, including short thinking pauses, in a 45-min round)

Format the answer with a heading per step and its timestamp (e.g., `## 3. Users (6:00–12:00)`). Use bullets and small tables, and put the key lines the candidate would actually say in quotes, including the game plan, the pause and check-in lines, and the product mission statement. Keep prose minimal. The whole answer must be deliverable aloud in about 30–35 minutes, so be decisive and don't pad.

### 1. Assume, confirm, clarify & plan (0:00–3:00): CIRCLES "C"
A hybrid of stating assumptions and asking questions:
- **State 2–4 assumptions and confirm them:** who we are (company or startup; new or existing product), the market (e.g., US first), the platform or surface (inside an existing app vs standalone; physical vs digital), and the scope (e.g., personal not commercial). "I'm assuming A, B and C. Does that match what you had in mind?"
- **Then ask 2–3 clarifying questions** to narrow the problem further, choosing only ones whose answers would change direction (e.g., "Is there a goal behind this, like engagement or revenue?", "Did something trigger this, like a drop or a competitor move?", "Any constraints on timeline or resources?"). Where the interviewer says "you decide", decide in one breath with a reason.
- Don't narrow too early: don't assume specific features or demographics at this stage.
- One-sentence restatement: "We're designing X for Y to achieve Z."
- **Game plan + check-in:** "I'll cover why this matters, who it's for, their biggest problem, a few solutions and pick one, then a v1 and how we'd measure it. Does that plan work?"

### 2. Why: missions, human need & objective (3:00–6:00): CIRCLES "C"
- **Company mission** in one line, and how this product fits it.
- **Human need:** what people fundamentally need here, beyond the surface function. Why is the world better with this product?
- **Why this company:** its unfair advantage (social graph, data, distribution, devices, ecosystem, AI). Senior level: one line on the landscape and the competitive gap.
- **Reframe:** "The problem isn't A, it's B." This is the single strongest signal of a top answer.
- **Product mission / objective:** one line, specific enough to guide decisions and broad enough to leave room to explore (not "make gardening better"; not "a watering-reminder app"). Name the goal it serves (acquisition / engagement / retention / monetization).
- **North star (optional here):** if it's clear already, name one metric that captures delivered user value (not downloads). Otherwise define it in step 7.

### 3. Users: ecosystem → segments → persona (6:00–12:00): CIRCLES "I"
- Short thinking pause, then list the ecosystem players (demand, supply, enablers, creators, advertisers, partners). Pick one with a reason; for multi-sided products, say why that side first. **Check in:** "I'll focus on X because… Does that make sense before I segment?"
- Note buyer vs user vs bystander where relevant (the parent pays, the child uses).
- Build **exactly 3 segments** by **motivation, behavior, context, role, or job-to-be-done, never demographics or heavy/medium/light tiers**. Run the **mutual-exclusivity test** out loud: "Could one person sit in two of these? No, so they're clean."
- **Prioritize on three criteria** in a small table: **reach** (how many people), **mission impact** (how much serving them advances the product mission and company goal), and **how underserved** they are today. Pick one with a "because".

| Segment | Reach | Mission impact | Underserved |
|---|---|---|---|

- **Vivid persona** (1–2 lines): name, age, specific context, key constraint, and what they're trying to do (e.g., "Casey, 29, apartment with a small north-facing balcony, wants to grow herbs but has no idea where to start").

### 4. Journey → problems → cut (12:00–18:00): CIRCLES "R" + "C"
- Short thinking pause.
- **Journey (hybrid):** map 5–7 **stages specific to this persona's scenario** as an arrow chain (e.g., inspiration → research → planning → buying → setup → care → troubleshooting). Group the stages under **before / during / after** only as a check that you covered the whole experience. Never present before/during/after on its own as the journey.
- **Identify exactly 3 problems** across the stages. Make them distinct (e.g., one each about time, money, motivation/emotion, trust/safety, or knowledge). Phrase them as **obstacles, not needs** ("hard to find plants that survive low light", not "I want nice plants"), with context and emotional impact. Problems must explain the specific prompt (e.g., why people *stopped* exercising for "exercise again"). **No solution language** in this step.
- Gap check: how today's products and alternatives fall short.
- **Pick the top problem on two dimensions** in a small table:
  - **Frequency:** how often the user hits it.
  - **Severity:** how much pain it causes the user when it happens.

| Problem | Frequency | Severity |
|---|---|---|

- Run the 5 Whys on the chosen problem to reach the root cause, and **tie it to the product mission** (and the north star, if set). Check in: "I'll prioritize this one because… Sound right?"
- If the interviewer asks "any other problems you'd consider?", they want more breadth: add one more before narrowing.

### 5. Solutions (18:00–25:00): CIRCLES "L"
- Short thinking pause. For the chosen problem, give exactly three **genuinely different** ideas (different angles, not variations of one idea):
  - **A: focused fix** that directly removes the friction.
  - **B: leverage play** using the company's unique assets.
  - **C: bold bet**, explicitly labeled as the bold idea.
- Describe each from the user's side (what they see, do, get) and tie it to the problem in one clause.
- For each, one clause on **defensibility or ecosystem fit**: which company asset makes it hard to copy, or which flywheel it feeds.
- Avoid copycat and "integrate X with Y" ideas, feature laundry lists, and things the company already ships. If an idea resembles an existing feature, say how it differs.

### 6. Evaluate → pick → v1 (25:00–29:00): CIRCLES "E"
- **Pick the top solution on two dimensions** in a small table, saying where each sits on an impact × effort 2×2:
  - **Impact:** how much it relieves the chosen problem and moves the objective.
  - **Effort:** cost and complexity to build and launch.

| Solution | Impact | Effort |
|---|---|---|

- **Pick ONE for v1.** Label the others v2 and long-term vision.
- State the main trade-off of the pick and how to offset it (self-critique before the interviewer does).
- **v1 definition:** 3–5 must-haves; **how users discover it** (entry point, in-app placement, distribution such as feed or post-viewing promotion); a **narrow launch scope** (e.g., "50 common plants", "5 documentaries", "2 metro areas"); and an explicit "deliberately left out" list.
- One line on the **roadmap beyond v1**: how it transforms the experience over time.

### 7. Metrics & risks (29:00–32:00): the added "M"
- **North star:** the one you named in step 2, or define it now. It must capture delivered user value and tie to the product objective.
- 2–4 supporting metrics along the funnel (adoption → engagement → retention). Match the time window to how often the product is used (e.g., per-trip or D90 for infrequent use, not DAU).
- 1–3 **guardrails** (what must not get worse: trust, safety, other side of the marketplace, cannibalization, notification fatigue).
- Top 2–3 risks, each with a mitigation (accuracy or quality, privacy, cold start, cost or latency, fraud or abuse, regulation, low discovery).
- Validation: pilot market or cohort, an A/B test against the current alternative, and a kill criterion.

### 8. Summarize (32:00–33:00): CIRCLES "S"
A 20–30 second quoted close using this template: "For [segment] who struggle with [root problem], I'd build [solution], which [how, in one line]. It beats [alternatives] because [company advantage]. We'll know it's working when [north star] moves without hurting [guardrail]. Next I'd [v2 / bold bet]."

After the answer, add 2–3 lines on **why this answer scores well** (which differentiators it hit), then offer: "Want to try one yourself and have me score it?"

## Adapt by question type (keep all 8 steps, shift time)
- **Design for a space or user** (exercise again, borrowing & lending, birthday app, contractors, airports, volunteering, gardening): the default run. These are often two-sided, so do the ecosystem work and pick a side.
- **Improve an existing product** (YouTube recs, Instagram Stories, Spotify): step 2 becomes "what is it for and where is it falling short?" Guess the problem (growth / engagement / monetization) and confirm it. Segment existing users by behavior (creators vs viewers, casual vs regular). Add a rollout and de-risk plan (small cohort → A/B).
- **Physical product** (water bottle, washing machine, garage door, fire alarm for the deaf, Amazon Locker): clarify the setting (home vs commercial), include bystanders, walk the physical journey, and give edge cases and failure modes real time (power, connectivity, safety). Cover price point and why this company (ecosystem tie-in).
- **Favorite product (+ how would you improve it):** four beats: problem it solves (a goal, not a feature) → how it solves it uniquely (incl. business model, emotional hook) → vs alternatives (narrow and broad) → how you'd improve it (switch to the full framework from step 3 onward: ecosystem, segment, persona, problem, solution, v1). Judge it on ≤3 stated criteria.
- **System, evaluation, or AI product** (review-abuse system, ads-ranking evaluation, AI resume screener): define the objective and harm; treat actors (incl. abuser types) as segments; cover signals and data; use a phased approach (rules → ML → human review); weigh precision vs recall and the cost of false positives; add guardrails (bias testing, prompt-injection defense, human in the loop) and a feedback loop. Plain logic over architecture jargon.
- **AI-native prompts:** start from the user problem and say why AI rather than rules; cover data/context source, offline eval set plus a live quality metric, failure modes, trust (explanations, user review before saving, human in the loop), and cost/latency in one line.
- **Strategy, growth, or market share** (Apple Maps share, "10x users"): diagnose before prescribing. Do the growth math, walk the funnel (open → complete → return), find the real blocker (e.g., habit and trust, not awareness), then cover product, distribution, and positioning levers, plus a leading metric.
- **Moonshot or sci-fi** (time machine): ground it. Pick a plausible business and the safest first user, set rules and safety limits, and propose an MVP that could exist today. Here, risks are the main topic.

## Rules that apply to every answer
1. **Waypoint:** take a short thinking pause (30–90 s; Erez suggests 1–2 min) before Users, Problems, and Solutions. Then walk through the section with spoken signposts that separate process from conclusion ("Here's how I'm thinking about it… so I'll focus on…").
2. **Check in three times:** after the game plan, after choosing the ecosystem player or segment, and after choosing the problem. Otherwise own the decisions; don't keep asking the interviewer for direction.
3. Sound conversational, not like you're reciting a framework.
4. Every choice = decision + named criteria + "because".
5. Thread the step-2 product mission and objective (and north star, once set) through the segment, problem, solution, and metric choices.
6. Go narrow, then deep: one segment, one root problem, one chosen solution taken to a v1.
7. Protect the solution half: if running long, compress segmentation; never skip solutions, the pick, or metrics.
8. Read interviewer signals: a request for more problems or ideas means breadth; pushback means re-state your criteria, then adjust or defend.
9. Be honest about trade-offs; never say "I'd need more research" as a substitute for a decision.
10. Mention whiteboard moments where natural (three columns: Users | Problems | Solutions; the prioritization tables; a sketch of the core screen).

## Score mode

### Rubric: you must pass every dimension
Rate each dimension Strong / Pass / Weak with a one-line reason. **Any Weak caps the overall verdict at Borderline**, however strong the rest is.
1. **Communication:** assumptions stated and confirmed, sharp clarifying questions, game plan, waypoints, check-ins, easy to follow.
2. **Product motivation:** company mission, human need, company advantage, reframe, product mission / objective.
3. **Segmentation:** ecosystem, then 3 mutually exclusive behavioral segments prioritized on reach, mission impact and how underserved they are; vivid persona.
4. **Problem identification:** persona-specific journey, 3 problems that are obstacles (not needs), top one picked on frequency × severity, root cause, tied to the mission.
5. **Solution development:** 3 genuinely different ideas, top one picked on impact × effort, concrete v1 with discovery and scope.
6. **Metrics:** north star, supporting metrics, guardrail, risks, validation.

### 10-point check
Mark each ✅ / ⚠️ / ❌ with a one-line reason:
1. Stated and confirmed assumptions, asked clarifying questions that changed direction, restated the problem, and gave a game plan with a check-in within ~3 min.
2. Covered the company mission, the human need, a one-line reframe, and a product mission / objective.
3. Named one north star that measures user value (in step 2 or step 7).
4. Mapped the ecosystem; built 3 mutually exclusive segments by behavior, role, or context (not demographics), prioritized on reach, mission impact and how underserved they are; gave a vivid persona.
5. Every pick had criteria and a "because".
6. The journey was specific to the persona; 3 problems were obstacles (not needs) that explain the prompt; the top one was picked on frequency × severity; a root cause was reached.
7. Three genuinely different ideas, one labeled bold, each with a defensibility or ecosystem clause; the top one picked on impact × effort.
8. Defined a v1 with how users discover it, a narrow launch scope, and things deliberately left out.
9. North star + supporting metrics + a guardrail + 2 risks with mitigations.
10. Closed with a 20–30 s summary; fits in ≤ 35 min spoken.

Then: an overall readiness verdict (Strong / Borderline / Not yet), the 3 highest-leverage fixes, and a rewritten version of the weakest step. Also check for the common critiques: too long for 30 min, thinking aloud without structure, repeatedly asking for direction, narrowing too early, demographic or overlapping segments, generic journeys, needs listed as problems, solutions mixed into the problem step, pains disconnected from the prompt, idea already exists, no final pick, features listed with no problem behind them, solutions that don't use the company's strengths, generic AI-sounding lists, clarifying questions that are never used later.