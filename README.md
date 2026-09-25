# PM Interview Skills for Claude

Three free, open-source [Claude skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) for preparing for Product Manager interviews. Give Claude an interview question and get a structured, interview-ready model answer. You can also paste in your own answer to get it scored, or ask Claude to run a mock interview.

| Skill | Question types | Framework |
| --- | --- | --- |
| [`product-sense-interview`](skills/product-sense-interview/SKILL.md) | Design X, improve X, favorite product | 8-step **CIRCLES+M** |
| [`pm-metrics-interview`](skills/pm-metrics-interview/SKILL.md) | Measure success, north star, metric dropped, A up / B down, should we ship | **STARTS** |
| [`pm-execution-interview`](skills/pm-execution-interview/SKILL.md) | Success metrics, metric drop, trade-offs, launch, experiment design | 6-step **C-G-M-A-D-S** playbook with modules and overlays |

The frameworks draw on *Cracking the PM Interview* (McDowell & Bavaro), *Decode and Conquer* (Lewis Lin), and an analysis of top-voted public answers to popular PM interview questions.

## Install

### Claude.ai (web or desktop app)

1. Download this repo (**Code → Download ZIP**) and unzip it.
2. Zip each skill folder on its own, for example `skills/product-sense-interview` → `product-sense-interview.zip`. The zip must contain the folder with `SKILL.md` inside it.
3. In Claude, open **Settings → Capabilities → Skills**, choose **Upload skill**, and upload each zip.

### Claude Code

Copy the skills into your personal skills folder:

```bash
git clone https://github.com/<your-username>/pm-interview-skills.git
cp -R pm-interview-skills/skills/* ~/.claude/skills/
```

Restart Claude Code. The skills then load automatically when you ask a matching question, or you can call them directly, for example `/product-sense-interview`.

## Example prompts

- "You're a PM at Spotify. Design a feature to help people discover podcasts."
- "How would you measure success for Instagram Stories?"
- "DAU for Uber Eats dropped 10% last week. What do you do?"
- "Mock me on a metrics question."
- "Score my answer: …" (then paste your answer)

## Contributing

Issues and pull requests are welcome. If a framework step could be clearer, or you have a question type the skills handle poorly, please open an issue.

## License

[MIT](LICENSE): free to use, copy, modify, and share, including commercially.
