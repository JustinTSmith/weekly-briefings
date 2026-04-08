# Intelligence Briefings

Automated weekly and monthly briefings on AI, technology, and solopreneur business opportunities — generated from a curated newsletter stack enriched with live web research and written by Claude.

Not a summary. An analyst that reads everything, finds the signal, and tells you what to build next.

---

## Newsletter Sources

Newsletters are pulled from Gmail and tiered by signal quality. Each tier carries a different synthesis weight — Foundation ideas carry 4× more influence on the briefing than noise from Other. To add or move a source, relabel it in Gmail and update `config.py` → `NEWSLETTER_TIERS`.

### 🏛 Foundation
*The highest-conviction sources. Long-form, first-principles thinking from people with a strong track record of being right before it's obvious. These shape the analytical frame — not the news cycle. Weight: 2.0×*

- **[Paul Graham](https://paulgraham.com)** — Periodic essays on startups, founders, and what's worth building. Dense with applicable principles; one essay often contains more signal than a month of tactical newsletters.
- **[Venkatesh Rao / Ribbonfarm](https://www.ribbonfarm.com)** — Long, systems-level essays on technology, culture, and how complex things actually work. Slow to read, high residual value.

### 🔍 Reality Check
*Practitioner analysis and empirical takes. These sources challenge hype with data, benchmark claims against evidence, and cover the structural forces shaping tech and business. Weight: 1.8×*

- **[Gary Marcus](https://garymarcus.substack.com)** — The most rigorous AI sceptic writing today. Strong on benchmark critique, capability gaps, and what LLMs still can't do reliably. Essential counterweight to hype.
- **[Noah Smith / Noahpinion](https://noahpinion.blog)** — Macro economist turned tech analyst. Excellent on industrial policy, AI's economic impact, and long-run structural trends. Data-heavy, well-reasoned.
- **[Ethan Mollick / One Useful Thing](https://www.oneusefulthing.org)** — Wharton professor who actually uses AI tools in his work and publishes findings. Rigorous on what works, what doesn't, and how to think about human-AI collaboration.
- **[Import AI](https://importai.substack.com)** — Jack Clark's weekly digest of AI research papers and capability developments. Dense technical summary; useful for tracking what's actually advancing vs. marketing.
- **[Nate's Substack](https://natesnewsletter.substack.com)** — Focused on AI agent architecture, orchestration patterns, and the practical plumbing of multi-agent systems. Useful for building, not just watching.
- **[Stratechery](https://stratechery.com)** — Ben Thompson's framework-driven tech strategy analysis. Best source for understanding platform dynamics, business model shifts, and why companies make the moves they make.
- **[The Batch](https://www.deeplearning.ai/the-batch/)** — Andrew Ng's weekly AI digest from DeepLearning.AI. Covers research, applications, and industry moves with a practitioner lens. Good signal-to-noise ratio.
- **[The Information](https://www.theinformation.com)** — Investigative tech journalism. Breaks stories before the press release, covers funding rounds, internal dynamics, and strategic moves that shape the industry.

### 🔨 Blueprint
*Tactical and operational. These sources tell you how to build, price, and sell — not just what to think about. Business model frameworks, founder playbooks, and product thinking from people doing it at scale. Weight: 1.5×*

- **[Lenny Rachitsky](https://www.lennysnewsletter.com)** — Deep dives on product, growth, and go-to-market from a former Airbnb PM turned researcher. Interviews top operators; data-backed takes on what actually drives retention and growth.
- **[Dan Martell / SaaS Academy](https://danmartell.com)** — SaaS-specific playbooks for founders. Strong on pricing, hiring leverage, and the operational mechanics of scaling a software business without burning out.
- **[Alistair Croll](https://alistair.substack.com)** — Co-author of *Lean Analytics*. Sharp on product strategy, metrics that matter, and the intersection of data and product decisions. Underrated.
- **[Ash Maurya / Lean Stack](https://leanstack.com)** — Creator of the Lean Canvas. Covers customer discovery, business model design, and how to stress-test ideas before building. Useful early in the opportunity pipeline.
- **[Arvid Kahl / The Bootstrapped Founder](https://thebootstrappedfounder.com)** — Built and sold a SaaS in 2 years with no VC. Writes exclusively about the zero-VC, micro-team, product-led model — audience building, monetisation without external capital, and when to sell. The most direct voice for the $1–3M lean business thesis on this list.
- **[Demand Curve](https://www.demandcurve.com/newsletter)** — Julian Shapiro's growth mechanics newsletter. Publishes what's actually working in cold email, content marketing, SEO, and organic acquisition — with data. The most rigorous free growth newsletter available. Fills the distribution gap directly.
- **[Luke Sophinos / Vertical Software & AI](https://www.newsletter.lukesophinos.com)** — Built and sold a vertical SaaS. Covers the operating mechanics of niche software businesses: pricing power, churn, customer concentration, and when to layer AI on an existing workflow. The dedicated feed for the "boring business + AI" thesis.
- **[Every](https://every.to)** — Bundle of AI-native writers covering business, productivity, and the craft of building with LLMs. Strong on the "how do you actually use this" layer that most AI coverage misses.
- **[Not Boring](https://www.notboring.co)** — Packy McCormick's long-form analysis of interesting companies and business models. Excellent for understanding what makes a specific business work and why it's defensible.
- **[CEO Dinner](https://ceodinner.com)** — Condensed founder wisdom and operator takes. Useful for pattern-matching across how founders at different stages think about the same problems.
- **[John Cutler / Cutlefish](https://cutlefish.substack.com)** — The most thoughtful writer on product management and organisational dynamics. Essential if you're building anything involving teams, prioritisation, or product culture.

### ⚡ Edge
*Early signals and ambient awareness. These sources surface what's launching, what developers are building, and what's entering the discourse before it becomes consensus. Lower analytical depth, high breadth. Weight: 1.5×*

- **[Ben's Bites](https://www.bensbites.com)** — Daily AI news digest. Best for catching product launches, funding rounds, and model releases within 24 hours. Broad, fast, well-curated.
- **[Latent Space](https://www.latent.space)** — swyx and Alessio's AI engineering newsletter. Deep dives on agents, evals, RAG, memory, orchestration, and model architecture — written by and for people building with LLMs. The most important AI engineering publication not yet in this stack; fills the implementation-depth gap that Import AI and The Batch leave open.
- **[Simon Willison](https://simonwillison.net)** — Hands-on LLM developer and creator of Datasette. Posts detailed notes on what he's building and what he's observing. Strong leading indicator of where developer tooling is heading.
- **[Greg Isenberg / Late Checkout](https://gregisenberg.com)** — AI business idea generation and solopreneur opportunity analysis. High volume, uneven quality — but useful for spotting the shape of emerging micro-markets.
- **[TLDR](https://tldr.tech)** — Developer-facing tech news digest. Good for ambient awareness of what engineers are discussing, what tools are gaining traction, and what just shipped.
- **[Replit](https://replit.com)** — Product updates and community signals from the leading browser-based coding platform. Useful for tracking the AI coding market and what non-technical builders are doing.
- **[Morning Brew](https://www.morningbrew.com)** — Business and tech news with a broad lens. Background signal on macro business moves; useful for context rather than depth.
- **[Pirate Wires](https://www.piratewires.com)** — Tech culture, politics, and the ideological currents running through Silicon Valley. Useful for understanding the social context in which tech companies operate.

### 🧘 Personal Development
*Mental models, philosophy, and performance. Lower synthesis weight — included for cross-domain pattern recognition rather than direct business signal. Weight: 0.8×*

- **[Sam Harris / Making Sense](https://samharris.org)** — Long-form exploration of consciousness, technology, ethics, and rationality. Useful for stress-testing assumptions and thinking clearly about things that matter.
- **[Mark Manson](https://markmanson.net)** — Counterintuitive takes on values, priorities, and decision-making. Better than the self-help genre it superficially resembles; focused on what actually matters vs. what feels productive.
- **[Cory Muscara](https://corymuscara.com)** — Mindfulness and performance at the intersection of neuroscience and contemplative practice. Useful for attention, focus, and managing the psychological load of building.
- **[James Clear](https://jamesclear.com)** — Habits, systems, and incremental improvement. Widely read for a reason — practical frameworks for behaviour change with solid research backing.
- **[Ryan Holiday](https://ryanholiday.net)** — Stoic philosophy applied to modern challenges. Strong on ego, resilience, and operating under pressure. More useful during hard stretches than easy ones.
- **[Benjamin Hardy](https://benjaminhardy.com)** — Psychology of identity, future self, and deliberate change. Occasionally too motivational in tone, but the underlying frameworks on how people change are solid.

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
