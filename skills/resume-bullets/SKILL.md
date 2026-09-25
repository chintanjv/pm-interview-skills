---
name: "resume-bullets"
description: Generates 16 tailored, ATS-friendly resume bullet points/achievements for a specific job. Use this skill whenever the user provides job details (job title, job description, responsibilities, qualifications, and/or requirements) and asks for resume bullet points, achievements, resume lines, or wants their resume tailored to that role — even if they don't say the word "skill" or "bullet points" explicitly, e.g. "help me tailor my resume for this PM role" or "write achievements for this job posting." Always follow the exact rules, self-check, and output format in this skill rather than improvising a different resume-writing approach.
---

# Resume Bullet Point Generator

Produces exactly 16 tailored, one-line resume achievements for a specific job. The bullets use the posting's own language and priorities, so they read as if written by someone who already has the role's core skills and has demonstrated them with real impact.

## Step 1: Confirm you have the inputs

Required:
- **Job title**
- **Job description / responsibilities** (what the role does day to day)
- **Qualifications / requirements** (what the employer screens for)

Optional (use if provided): seniority level, industry, company name/type, tools or platforms named in the posting, and the user's own resume/background.

If the user gives only a job title, ask them to paste the posting (or at least the responsibilities and qualifications sections) before generating. If they have given title + description + requirements, do not ask for anything else — proceed.

## Step 2: Extract the posting's language (do this before writing)

Silently build two lists from the posting:
1. **Responsibility areas** — the distinct themes the role covers (e.g., experimentation, roadmap, stakeholder management, AI/ML, monetization).
2. **Exact keywords** — the posting's own nouns, tools, and phrases, copied verbatim (keep their spelling, capitalization, and hyphenation).

Every bullet must draw from these lists. Do not substitute synonyms for posting terms (if the posting says "cross-functional partners," do not write "stakeholders"; if it says "A/B testing," do not write "split testing").

## Step 3: Write 16 bullets

Each bullet must satisfy ALL of the rules below. If two rules conflict, follow the priority order at the end of this step.

1. **Relevance** — maps to something explicitly in the posting's responsibilities, qualifications, or requirements. No generic achievements that could fit any job.
2. **Quantified impact** — includes one specific, plausible metric (%, $, time saved, users, scale) reflecting outcomes this role values. Avoid suspiciously round or inflated numbers; vary metric types across the set.
3. **Keyword coverage** — uses the posting's exact terminology from Step 2.
4. **Acronym + full form** — when a bullet uses an acronym for a key term or tool, write the full form followed by the acronym in parentheses, e.g., "click-through rate (CTR)." Do this in every bullet where the acronym appears, since each bullet may be copied into a resume independently. Use at most two expansions per bullet to keep it readable; well-known terms that the posting itself never expands (e.g., "AI," "API," "SQL") don't need expansion.
5. **Industry-standard phrasing** — verbs and framing practitioners in this field actually use; no corporate filler ("leveraged synergies," "results-driven," "various," "helped to").
6. **A compelling hook** — a concrete mechanism or specific result that makes a hiring manager want to ask "tell me more." Specific beats flashy: never invent implausible "twists."
7. **A hint of storytelling** — where it fits naturally, imply challenge → action → result in one line. Skip it if it makes the bullet clunky or too long.
8. **Resume grammar (strict)**:
   - Start with a strong, past-tense action verb (e.g., "Launched," not "Launching" or "Responsible for"). Use a high-impact action verb, wherever applicable ("Spearheaded", "Orchestrated", "Championed", "Leveraged", "Collaborated", etc.)
   - Keep all verbs in the bullet in the same tense and in parallel form (e.g., "Built X and scaled Y," not "Built X and scaling Y").
   - No first-person pronouns (I, me, my, we, our) and no period at the end.
   - Every modifier must attach clearly to what it describes. Avoid a trailing ", resulting in…" or ", using…" clause after a noun it doesn't logically modify; prefer "to drive," "that cut," "by," or "via" constructions instead.
   - Use articles ("a," "an," "the") where standard English requires them; resume style drops pronouns, not articles.
   - Hyphenate compound modifiers before nouns ("data-driven roadmap," "cross-functional team," "high-intent users").
   - Format numbers consistently: numerals for all metrics, "%" with no space, "$" before amounts, "K/M/B" for thousands/millions/billions (e.g., "$4.2M," "35%," "12K users").
9. **No repeated opening verbs** — all 16 bullets start with a different verb.

**Priority when rules conflict:** grammar and one-line length (8) > relevance (1) > keyword coverage (3) > quantified impact (2) > acronym expansion (4) > hook (6) > storytelling (7). Cut storytelling or the hook before breaking grammar or length.

**Coverage across the set:**
- Every responsibility area from Step 2 gets at least one bullet.
- Vary the kind of achievement across the 16: leadership/ownership, cross-functional collaboration, technical/domain execution, process or efficiency improvement, and business outcome. The set should read as one well-rounded candidate, not 16 variations of one accomplishment.

**If the user provided their own background:** ground bullets in their real experience and employers; do not invent roles, companies, or scope they didn't describe. Where a metric isn't given, use a plausible placeholder metric consistent with what they told you.

## Step 4: Self-check before responding (mandatory)

Silently review every bullet against this checklist and rewrite any that fail. Do not output until all 16 pass:
- [ ] Exactly 16 bullets
- [ ] Starts with a past-tense action verb; no two bullets share the same opening verb
- [ ] Grammatically correct as a standalone line: consistent tense, parallel verbs, correct articles, no dangling modifiers, no run-ons
- [ ] Contains at least one posting keyword, copied exactly
- [ ] Contains one plausible metric
- [ ] Acronyms expanded per rule 4
- [ ] Across the set: every responsibility area covered; achievement types varied

If code execution is available, verify word and character counts programmatically rather than by estimate.

## Output format

Return only the 16 bullets as a bullets list — no preamble, headings, or explanation unless the user asks. Example shape (content varies entirely by role):

```
- Launched [feature from posting] for [segment], lifting [metric from posting] by [X%] in [timeframe]
- Partnered with [cross-functional team from posting] to ship [thing], cutting [cost/time] by [X]
...
- ...
```

## If the user wants iteration

If they ask to tighten, re-tailor toward a specific requirement, swap in real details from their background, or make bullets punchier, edit the existing set — don't generate an unrelated new set unless asked. Keep the count at 16 unless they explicitly request a different number. Re-run the Step 4 self-check on every edited bullet.
