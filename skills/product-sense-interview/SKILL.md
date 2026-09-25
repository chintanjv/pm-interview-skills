---
name: "product-sense-interview"
description: "Answer a PM product design / product sense interview question (design X, improve X, favorite product) using the 8-step CIRCLES+M framework, or score a practice answer."
---

# Product Sense Interview: CIRCLES+M

Use this skill when the user gives a product design / product sense interview question (e.g., "You're a PM at Meta. Design a product for group travel", "Improve Spotify", "Design a fire alarm for the deaf", "What's your favorite product?") and wants a model answer, OR asks to have their own answer scored.

The framework was built from *Cracking the PM Interview* (McDowell & Bavaro), *Decode and Conquer* (Lewis Lin, CIRCLES), and an analysis of 112 top-voted 2023–26 Exponent answers across 25 questions. Core finding: top answers use the same spine as everyone else. What separates them is (1) a one-line reframe of the real problem, (2) explicit prioritization with named criteria and a "because", (3) committing to ONE solution with an MVP, and (4) metrics with guardrails plus risks. Clarifying questions and reciting the mission are table stakes; they do not differentiate.

## Mode selection
- **Answer mode (default):** the user gives a question → produce a complete, interview-ready answer following the 8 steps below.
- **Score mode:** the user pastes their own answer or transcript → score it with the 10-point check at the bottom, give the 3 highest-leverage fixes, and rewrite the weakest step.
- If the question is actually metric diagnosis ("DAU dropped 10%"), estimation, pure strategy ("should X enter Y"), or an execution trade-off, say so in one line and use a better-suited structure instead of forcing this framework.

## Answer mode: the 8 steps (≈30–33 min spoken)

Format the answer with a heading per step and its timestamp (e.g., `## 3. Users (5:00–11:00)`). Use bullets and small tables, and put the key lines the candidate would actually say in quotes. Keep prose minimal. The whole answer must be deliverable aloud in about 30 minutes, so be decisive and don't pad.

### 1. Clarify & restate (0:00–2:00): CIRCLES "C"
- Ask only 3–4 questions whose answers change direction: who are we (company or startup; new or existing product), what is it (physical or digital; standalone or inside an app; scope), why and what goal, constraints (geography, platform, timeline).
- Where the interviewer would say "you decide", decide in one breath with a reason (e.g., US first, mobile, 12 months).
- End with a one-sentence restatement: "We're designing X for Y to achieve Z."

### 2. Why & goal (2:00–5:00): CIRCLES "C"
- Company mission in one line and how this product fits it.
- **Why this company:** its unfair advantage (social graph, data, distribution, devices, ecosystem, AI).
- Senior level: one line on the landscape and the competitive gap.
- **Reframe (mandatory):** "The problem isn't A, it's B." This is the single strongest signal of a top answer.
- Commit to ONE goal (acquisition / engagement / retention / monetization) and a **north-star metric** that captures delivered user value (not downloads).

### 3. Users: ecosystem → segments → pick one (5:00–11:00): CIRCLES "I"
- List the ecosystem players (demand, supply, enablers). For multi-sided products, choose a side and say why.
- Note buyer vs user vs bystander where relevant (the parent pays, the child uses).
- Build 3–4 non-overlapping segments by **behavior, context, role, or job-to-be-done, never demographics or heavy/medium/light tiers**.
- Score them in a small table on reach × pain/underserved × fit with goal and company advantage. Pick one with a "because".
- A one-line persona (name, context, what they're trying to do).

### 4. Journey → pains → cut (11:00–17:00): CIRCLES "R" + "C"
- Walk the journey (before → during → after) as an arrow chain.
- List 4–6 **distinct** pains spanning time, money, motivation/emotion, trust/safety, and knowledge. Pains must explain the specific prompt (e.g., why people *stopped* exercising for "exercise again"). No solutions disguised as pains.
- Gap check: how today's products and alternatives fall short.
- Run the 5 Whys on the top pain to reach the root cause.
- Prioritize in a table by frequency × severity (plus goal fit). Pick 1 (max 2) root pain(s), tied back to the north star.

### 5. Solutions (17:00–24:00): CIRCLES "L"
- Exactly three **genuinely different** ideas for the chosen pain:
  - **A: focused fix** that directly removes the friction.
  - **B: leverage play** using the company's unique assets.
  - **C: bold bet**, explicitly labeled as the bold idea.
- Describe each from the user's side (what they see, do, get) and tie it to the pain in one clause.
- Avoid copycat and "integrate X with Y" ideas, feature laundry lists, and things the company already ships. If an idea resembles an existing feature, say how it differs.

### 6. Evaluate → pick → MVP (24:00–27:00): CIRCLES "E"
- Small table: impact on north star / effort / risk for A, B, C.
- **Pick ONE for v1.** Label the others v2 and long-term vision.
- State the main trade-off of the pick and how to offset it (self-critique before the interviewer does).
- MVP: 3–5 must-haves plus an explicit "deliberately left out" list.

### 7. Metrics & risks (27:00–29:30): the added "M"
- **North star** (same as step 2).
- 2–4 supporting metrics along the funnel (adoption → engagement → retention). Match the time window to how often the product is used (e.g., per-trip or D90 for infrequent use, not DAU).
- 1–3 **guardrails** (what must not get worse: trust, safety, other side of the marketplace, cannibalization, notification fatigue).
- Top 2–3 risks, each with a mitigation (privacy, cold start, fraud/abuse, regulation, low frequency).
- Validation: pilot market or cohort, an A/B test against the current alternative, and a kill criterion.

### 8. Summarize (29:30–30:00): CIRCLES "S"
A 20–30 second quoted close using this template: "For [segment] who struggle with [root pain], I'd build [solution], which [how, in one line]. It beats [alternatives] because [company advantage]. We'll know it's working when [north star] moves without hurting [guardrail]. Next I'd [v2 / bold bet]."

After the answer, add 2–3 lines on **why this answer scores well** (which differentiators it hit), then offer: "Want to try one yourself and have me score it?"

## Adapt by question type (keep all 8 steps, shift time)
- **Design for a space or user** (exercise again, borrowing & lending, birthday app, contractors, airports, volunteering): the default run. These are often two-sided, so do the ecosystem work and pick a side.
- **Improve an existing product** (YouTube recs, Instagram Stories, Spotify): step 2 becomes "what is it for and where is it falling short?" Guess the problem (growth / engagement / monetization) and confirm it. Segment existing users by behavior (creators vs viewers, casual vs regular). Add a rollout and de-risk plan (small cohort → A/B).
- **Physical product** (water bottle, washing machine, garage door, fire alarm for the deaf, Amazon Locker): clarify the setting (home vs commercial), include bystanders, walk the physical journey, and give edge cases and failure modes real time (power, connectivity, safety). Cover price point and why this company (ecosystem tie-in).
- **Favorite product:** four beats: problem it solves (a goal, not a feature) → how it solves it uniquely (incl. business model, emotional hook) → vs alternatives (narrow and broad) → how you'd improve it (switch to the full framework). Judge it on ≤3 stated criteria.
- **System, evaluation, or AI product** (review-abuse system, ads-ranking evaluation, AI resume screener): define the objective and harm; treat actors (incl. abuser types) as segments; cover signals and data; use a phased approach (rules → ML → human review); weigh precision vs recall and the cost of false positives; add guardrails (bias testing, prompt-injection defense, human in the loop) and a feedback loop. Plain logic over architecture jargon.
- **AI-native prompts:** start from the user problem and say why AI rather than rules; cover data/context source, offline eval set plus a live quality metric, failure modes, trust (explanations, user control, human in the loop), and cost/latency in one line.
- **Strategy or market share** (Apple Maps share): diagnose before prescribing. Walk the funnel (open → complete → return), find the real blocker (e.g., habit and trust, not awareness), then cover product, distribution, and positioning levers, plus a leading metric.
- **Moonshot or sci-fi** (time machine): ground it. Pick a plausible business and the safest first user, set rules and safety limits, and propose an MVP that could exist today. Here, risks are the main topic.

## Rules that apply to every answer
1. State the roadmap once (one sentence), then sound conversational, not like reciting a framework.
2. Every choice = decision + named criteria + "because".
3. Thread the step-2 goal and north star through the segment, pain, solution, and metric choices.
4. Go narrow, then deep: one segment, one root pain, one chosen solution taken to a v1.
5. Protect the solution half: if running long, compress segmentation; never skip solutions, the pick, or metrics.
6. Be honest about trade-offs; never say "I'd need more research" as a substitute for a decision.
7. Mention whiteboard moments where natural (three columns: Users | Pains | Solutions; a sketch of the core screen).

## Score mode: 10-point check
Mark each ✅ / ⚠️ / ❌ with a one-line reason:
1. Restated the problem in one sentence within ~2 min.
2. Gave a one-line "the real problem is…" reframe.
3. Committed to one goal and one north star that measures user value.
4. Mapped the ecosystem and segmented by behavior, role, or context (not demographics).
5. Every pick had criteria and a "because".
6. Pains explain the specific prompt; a root cause was reached.
7. Three genuinely different ideas, one labeled bold.
8. Picked one and defined a v1 with things deliberately left out.
9. North star + supporting metrics + a guardrail + 2 risks with mitigations.
10. Closed with a 20–30 s summary; fits in ≤ 35 min spoken.

Then: an overall readiness verdict (Strong / Borderline / Not yet), the 3 highest-leverage fixes, and a rewritten version of the weakest step. Also check for the common critiques: too long for 30 min, pains disconnected from the prompt, idea already exists, no final pick, generic AI-sounding lists, clarifying questions that are never used later.