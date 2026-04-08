# Intelligence Briefings

Personal weekly and monthly intelligence briefings focused on AI, technology, and solopreneur-scale business opportunities. Generated automatically from a curated newsletter stack enriched with live web research.

---

## Output

| Cadence | Format | Location |
|---------|--------|----------|
| Weekly | `YYYY-MM-DD.md` | repo root |
| Monthly | `monthly/monthly-Mon-Mon-YYYY.md` | `monthly/` folder |

---

## How It's Generated

### Weekly Briefing — 3-Stage Pipeline

**Stage 1 — Local synthesis (DeepSeek-R1 via Ollama)**
Reads the full week of newsletters and produces structured analytical notes across themes, cross-domain connections, business signals, and weak signals. Runs entirely on local hardware (Mac Studio). No API cost.

**Stage 2 — Parallel live research**
Six workers run simultaneously:
- `last30days` skill — runs one search per synthesis section against Reddit, X/Twitter, YouTube, and Hacker News. Returns compact results including tweet cards, video links, and discussion threads.
- GitHub Trending (weekly) — scraped from github.com/trending
- ProductHunt Launches — fetched from the public Atom feed
- Funding Radar — TechCrunch funding RSS, filtered to AI/tech deals
- HN Who's Hiring — latest monthly thread from Algolia HN API, filtered for AI/ML/remote roles
- People signal — targeted `last30days` searches per topic to surface active practitioners worth following

**Stage 3 — Enriched writing (Claude Sonnet via Anthropic API)**
Takes all Stage 1 and Stage 2 outputs and writes the final briefing. Embeds tweet cards inline, links directly to source articles (Substack redirect URLs are decoded to clean article links), and applies conviction scoring to opportunities.

---

### Monthly Briefing — 3-Stage Pipeline

**Stage 1 — Local analysis (DeepSeek-R1 via Ollama)**
Reads 3 months of newsletters with temporal weighting: current month = 2×, prior two months = 1×. Produces deep analytical notes across themes, signals, and patterns.

**Stage 2 — Web search (DuckDuckGo via `ddgs`)**
Extracts search queries from the analysis and fetches relevant tools, GitHub repos, and resources to enrich the writing pass.

**Stage 3 — Writing (Claude Opus via Anthropic API)**
Writes a ~2500–3500 word monthly digest personalised to focus areas and business context.

---

## Newsletter Sources

Newsletters are pulled from Gmail and classified into tiers by signal quality:

| Tier | Weight | Description |
|------|--------|-------------|
| 🏛 Foundation | Highest | First-principles thinking, deep analysis |
| 🔍 Reality Check | High | Practitioner takes, empirical evidence |
| 🔨 Blueprint | Medium | Tactical implementation, how-tos |
| ⚡ Edge | Medium | Early signals, emerging tools |
| 📰 Other | Lower | General news, broader coverage |

Foundation-tier newsletters receive more context budget per newsletter and higher weighting in synthesis.

---

## Live Signal Sources

| Source | What it contributes |
|--------|-------------------|
| **last30days** | Reddit threads, X/Twitter posts, YouTube videos, HN discussions — per topic, run in parallel |
| **GitHub Trending** | What developers are actively building this week |
| **ProductHunt** | What's launching in adjacent spaces |
| **Funding Radar** | Recent AI/tech funding deals (TechCrunch RSS) |
| **HN Who's Hiring** | Monthly hiring signals filtered for AI/ML/remote roles |

**Tweet filtering:** Only tweets with 50+ likes are passed to the writing model, as a proxy for accounts with >1000 followers. The model is also instructed to skip low-audience accounts in the People Worth Following section.

**Article URL extraction:** Newsletter emails are parsed at the HTML level to extract `<a href>` links before text cleaning strips them. Substack redirect JWTs are decoded to expose clean article URLs. Tracking parameters (`utm_*`) are stripped.

---

## Briefing Sections

### Weekly

| Section | Description |
|---------|-------------|
| 🎯 **This Week's Signal** | The single most important shift this week — what changed, why it matters, 12-month implication |
| 🏗 **Build Opportunity Scan** | Per-opportunity analysis: ICP, `[noise]` / `[watch]` / `[act]` conviction, why now, path to $10k MRR |
| 📈 **Trend Velocity** | For each major theme: accelerating, plateauing, or fading — with evidence |
| 🔗 **Cross-Disciplinary Synthesis** | Where two unrelated signals rhyme across domains |
| 💡 **Contrarian Take** | One clear position against the week's consensus |
| 📊 **Weak Signals Worth Watching** | Early signals that don't have traction yet but pattern-match to things that matter |
| 🔁 **Resurface** | Key signals from 4 and 12 weeks ago re-examined with current context (spaced repetition) |
| ⚡ **Quick Hits** | 5–7 one-liners with links |
| 👥 **People Worth Following** | 6–8 practitioners worth adding to your feed — with specific reasons tied to this week's content |
| ✅ **This Week's 3 Actions** | Concrete next steps derived from `[act]`-rated opportunities |
| 📚 **Deep Reads for Later** | Direct links to source articles, decoded from newsletter email HTML |

### Monthly

Covers the same analytical framework across a 3-month rolling window, with deeper synthesis, cross-month pattern recognition, and web-sourced tool/repo recommendations.

---

## Persistence

Every weekly run saves:
- `weekly_archives/YYYY-MM-DD.md` — full markdown locally
- `weekly_archives/YYYY-MM-DD.json` — full research cache (tweets, research text, signal data, source index) so resends reproduce exact tweet cards without re-running the pipeline
- `opportunity_log.jsonl` — the Build Opportunity Scan section from every run, appended, for long-term pattern tracking

The `weekly_archives/` JSON cache enables `--resend` mode:
```bash
python3 weekly_enriched.py --resend   # resend last week's email from cache, no API calls
```

---

## Running

```bash
# Weekly enriched briefing (full pipeline)
cd ~/Workspace/scripts/gmail-automation
source .venv/bin/activate
python3 weekly_enriched.py

# Resend last week's from cache (no pipeline, no API cost)
python3 weekly_enriched.py --resend

# Monthly digest (runs automatically on schedule, or manually)
python3 main.py --monthly
```

A dedup guard prevents more than one full pipeline run per day. The monthly digest checks state before running and skips if already sent today.

---

## Stack

| Component | Tool |
|-----------|------|
| Newsletter ingestion | Gmail API (OAuth2) |
| Local LLM inference | Ollama — `deepseek-r1:latest` |
| Web research | `last30days` skill (Reddit · X · YouTube · HN) |
| Signal scraping | `requests` + `BeautifulSoup` |
| Weekly writing | Claude Sonnet (`claude-sonnet-4-6`) via Anthropic API |
| Monthly writing | Claude Opus (`claude-opus-4-6`) via Anthropic API |
| State / dedup | SQLite via `state_db.py` |
| Email delivery | Gmail API (sends to self) |
| Archiving | Local filesystem + this GitHub repo |
