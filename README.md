# Intelligence Briefings

Automated weekly and monthly briefings on AI, technology, and solopreneur business opportunities — generated from a curated newsletter stack enriched with live web research and written by Claude.

Not a summary. An analyst that reads everything, finds the signal, and tells you what to build next.

---

## Newsletter Sources

Newsletters are pulled from Gmail and tiered by signal quality. To add or move a source, relabel it in Gmail and update `config.py` → `NEWSLETTER_TIERS`.

### 🏛 Foundation
*First-principles thinking, long-form analysis, high prior probability of being right. Weight: 2.0×*
- [Paul Graham](https://paulgraham.com) — Essays on startups, technology, and thinking
- [Venkatesh Rao / Ribbonfarm](https://www.ribbonfarm.com) — Long-form systems and strategy essays

### 🔍 Reality Check
*Practitioner takes, empirical evidence, rigorous scepticism. Weight: 1.8×*
- [Gary Marcus](https://garymarcus.substack.com) — AI capability critique, benchmark analysis
- [Noah Smith / Noahpinion](https://noahpinion.blog) — Economic and macro structural analysis
- [Ethan Mollick / One Useful Thing](https://www.oneusefulthing.org) — Rigorous AI in practice research
- [Import AI](https://importai.substack.com) — Jack Clark's weekly AI research digest
- [Nate's Substack](https://natesnewsletter.substack.com) — AI agent architecture
- [Stratechery](https://stratechery.com) — Ben Thompson's rigorous tech strategy analysis
- [The Batch](https://www.deeplearning.ai/the-batch/) — DeepLearning.AI weekly research digest
- [The Information](https://www.theinformation.com) — Investigative tech industry reporting

### 🔨 Blueprint
*Tactical implementation, business frameworks, how-tos from people doing it. Weight: 1.5×*
- [Lenny Rachitsky](https://www.lennysnewsletter.com) — Product, growth, and AI in practice
- [Dan Martell / SaaS Academy](https://danmartell.com) — SaaS founder playbooks
- [Alistair Croll](https://alistair.substack.com) — Product strategy and lean analytics
- [Ash Maurya / Lean Stack](https://leanstack.com) — Lean startup and business model design
- [Every](https://every.to) — AI-native business practice and product writing
- [Not Boring](https://www.notboring.co) — Packy McCormick on business model analysis
- [CEO Dinner](https://ceodinner.com) — Founder network insights and playbooks
- [John Cutler / Cutlefish](https://cutlefish.substack.com) — Product management depth

### ⚡ Edge
*Early signals, emerging tools, things worth knowing before they're obvious. Weight: 1.5×*
- [Ben's Bites](https://www.bensbites.com) — Daily AI news and product launches
- [Simon Willison](https://simonwillison.net) — LLM tooling, developer signal, hands-on AI
- [Greg Isenberg / Late Checkout](https://gregisenberg.com) — AI business ideas and solopreneur opportunities
- [TLDR](https://tldr.tech) — Developer and tech news digest
- [Replit](https://replit.com) — Developer tools and product launches
- [Morning Brew](https://www.morningbrew.com) — Business and tech news pulse
- [Pirate Wires](https://www.piratewires.com) — Tech culture and politics

### 🧘 Personal Development
*Mental models, habits, and performance. Weight: 0.8×*
- [Sam Harris / Making Sense](https://samharris.org) — Philosophy, technology, long-form reasoning
- [Mark Manson](https://markmanson.net) — Values-based mental models and decision-making
- [Cory Muscara](https://corymuscara.com) — Mindfulness and performance
- [James Clear](https://jamesclear.com) — Habits and decision-making
- [Ryan Holiday](https://ryanholiday.net) — Stoicism and strategy
- [Benjamin Hardy](https://benjaminhardy.com) — Psychology and performance

---

## How It Works

### Weekly — 3 Stages

```
Gmail newsletters → DeepSeek-R1 (local) → parallel research → Claude Sonnet → your inbox + this repo
```

**Stage 1 — Synthesis (local, free)**
DeepSeek-R1 running on Ollama reads the week's newsletters and produces structured analytical notes: themes, cross-domain connections, weak signals, business opportunities.

**Stage 2 — Live research (parallel)**
Six workers run simultaneously against the synthesis:
- `last30days` — Reddit, X/Twitter, YouTube, HN per section
- GitHub Trending — what developers are actually building this week
- ProductHunt — what's launching in adjacent spaces
- Funding Radar — recent AI/tech deals via TechCrunch RSS
- HN Who's Hiring — monthly thread filtered for AI/ML/remote roles
- People signal — targeted searches to surface practitioners worth following

**Stage 3 — Writing (Claude Sonnet)**
Takes everything above and writes the final briefing. Decodes Substack redirect URLs to clean article links. Filters tweet cards to 50+ likes (proxy for >1,000 followers).

### Monthly — 3 Stages

Same analytical framework across a 3-month rolling window, with 2× weight on the current month. Opus writes the final ~3,000-word digest after a DuckDuckGo search pass for tools and repos.

---

## Sections (Weekly)

| | Section | Purpose |
|--|---------|---------|
| 🎯 | **This Week's Signal** | The single most important shift — what changed and the 12-month implication |
| 🏗 | **Build Opportunity Scan** | Opportunities with `[noise]` / `[watch]` / `[act]` conviction ratings, ICP, and path to $10k MRR |
| 📈 | **Trend Velocity** | Accelerating, plateauing, or fading — per major theme, with evidence |
| 🔗 | **Cross-Disciplinary Synthesis** | Where two unrelated signals rhyme |
| 💡 | **Contrarian Take** | One clear position against the week's consensus |
| 📊 | **Weak Signals** | Early patterns worth watching before they're obvious |
| 🔁 | **Resurface** | Signals from 4 and 12 weeks ago re-examined with current context |
| ⚡ | **Quick Hits** | 5–7 one-liners with links |
| 👥 | **People Worth Following** | 6–8 practitioners with specific reasons tied to this week |
| ✅ | **This Week's 3 Actions** | Concrete next steps from `[act]`-rated opportunities |
| 📚 | **Deep Reads** | Direct article links decoded from newsletter email HTML |

---

## Stack

| | Tool |
|--|------|
| Ingestion | Gmail API |
| Local LLM | Ollama — `deepseek-r1:latest` |
| Weekly writing | Claude Sonnet (`claude-sonnet-4-6`) |
| Monthly writing | Claude Opus (`claude-opus-4-6`) |
| Research | `last30days` skill + `requests` / `BeautifulSoup` |
| State / dedup | SQLite |
| Source | `~/Workspace/scripts/gmail-automation/` |
