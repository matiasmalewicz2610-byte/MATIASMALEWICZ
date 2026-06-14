# LinkedIn Organic Content Strategy for B2B SaaS
## Research Repository

> **Topic:** LinkedIn Organic Content Strategy for B2B SaaS
> **Built for:** 100Hires technical portfolio assignment
> **Repository:** github.com/matiasmalewicz2610-byte/linkedin-b2b-research
> **Status:** Active — YouTube transcripts collected · LinkedIn post collection pending

---

## What this is

This repository contains structured research on the 10 highest-signal practitioners in LinkedIn organic content strategy for B2B SaaS. It is the foundation for a practitioner-grade playbook on this topic.

The research was collected, curated, and organized using:
- An AI research agent (Claude) running inside Cursor IDE
- The Supadata API for YouTube transcript extraction
- Manual LinkedIn post collection via direct profile activity feeds
- Framework documentation extracted from newsletters and research reports

---

## Why this topic

LinkedIn Organic Content Strategy for B2B SaaS was selected because it sits at the intersection of three strengths: it has rich, accessible source material via YouTube (enabling API-based collection), its practitioners publish structured frameworks rather than generic advice (making it strong playbook material), and it directly maps to skills developed through years of institutional communications, graphic design, and advertising strategy work. Of the 8 candidate topics, this one had the clearest path from raw expert content to a usable, evidence-based playbook.

---

## Repository structure

```
research/
├── sources.md                          # Master list of all 10 experts with annotations
├── README.md                           # This file
├── linkedin-posts/                     # 10 files — one per expert — for post collection
│   ├── devin-reed.md
│   ├── dave-gerhardt.md
│   ├── richard-van-der-blom.md
│   ├── justin-welsh.md
│   ├── chris-walker.md
│   ├── brendan-hufford.md
│   ├── amanda-natividad.md
│   ├── katelyn-bourgoin.md
│   ├── peep-laja.md
│   └── april-dunford.md
├── youtube-transcripts/                # Transcripts organized by expert
│   ├── devin-reed/                     # 3 transcripts — ~26,000 words
│   ├── dave-gerhardt/                  # 3 transcripts — ~38,000 words
│   ├── richard-van-der-blom/           # 3 transcripts — ~35,000 words
│   ├── chris-walker/                   # 3 transcripts — ~47,000 words
│   └── april-dunford/                  # 3 transcripts — ~33,000 words
├── other/                              # Framework docs and research reports
│   ├── richard-van-der-blom-algorithm-report-2025.md
│   ├── amanda-natividad-zero-click-framework.md
│   └── april-dunford-positioning-notes.md
└── scripts/
    └── fetch-transcripts.js            # Supadata API script — all 15 video IDs pre-loaded
```

---

## The 10 experts

Experts were selected using 5 criteria weighted in this order:
1. Practitioner with documented real-world results — not just commentary
2. Content accessible via API or public collection
3. Framework richness — does their material support a playbook?
4. B2B SaaS specificity
5. Active audience engagement (verified at time of collection)

| # | Expert | Role | Tier | Primary source |
|---|--------|------|------|----------------|
| 1 | Devin Reed | Ex-Head of Content @Gong & @Clari | T1 | YouTube + LinkedIn |
| 2 | Dave Gerhardt | Ex-CMO @Drift · Founder @ExitFive | T1 | YouTube + LinkedIn |
| 3 | Richard van der Blom | LinkedIn Algorithm Report author | T1 | YouTube + LinkedIn |
| 4 | Justin Welsh | $5M+ ARR via organic LinkedIn only | T1 | LinkedIn + Newsletter |
| 5 | Chris Walker | Coined "dark social" + "dark funnel" | T2 | YouTube + LinkedIn |
| 6 | Brendan Hufford | 4-Part SaaS Growth Framework · 50+ SaaS clients | T2 | LinkedIn |
| 7 | Amanda Natividad | Creator of Zero Click Content framework | T2 | LinkedIn + Newsletter |
| 8 | Katelyn Bourgoin | Buyer psychology specialist · Customer Camp | T2 | LinkedIn + Newsletter |
| 9 | Peep Laja | Founder CXL + Wynter · messaging expert | T3 | LinkedIn |
| 10 | April Dunford | Positioning methodology · "Obviously Awesome" | T3 | YouTube + LinkedIn |

### Experts replaced during collection

Three experts were removed after verification showed no recent active LinkedIn posts:

| Removed | Replaced by | Reason |
|---------|-------------|--------|
| Matt Barker | Brendan Hufford | No active posts found at time of collection |
| Jasmin Alic | Katelyn Bourgoin | No active posts found at time of collection |
| Lara Acosta | Peep Laja | No active posts found at time of collection |

### Experts evaluated and rejected before final list

| Rejected | Reason |
|----------|--------|
| Luke Matthews | Posts present but low signal value — no actionable frameworks |

---

## YouTube transcripts collected

| Expert | Videos | Approx. words | Status |
|--------|--------|---------------|--------|
| Devin Reed | 3 | ~26,000 | ✅ Collected |
| Dave Gerhardt | 3 | ~38,000 | ✅ Collected |
| Richard van der Blom | 3 | ~35,000 | ✅ Collected |
| Chris Walker | 3 | ~47,000 | ✅ Collected |
| April Dunford | 3 | ~33,000 | ✅ Collected |
| **Total** | **15** | **~179,000** | |

---

## Obstacles and how they were solved

### 1. Git initialized from the wrong folder

**Problem:** Running `git init` from `C:\Users\Matias\OneDrive\Documentos` instead of the `research/` subfolder caused all personal files — Adobe Premiere projects, game saves, Zoom recordings — to be tracked and pushed to GitHub alongside the research repository.

**Solution:** Deleted the GitHub repository, re-initialized Git from inside the `research/` folder directly, and pushed a clean repository containing only the intended files.

**Lesson:** Always `cd` into the specific project folder before running `git init`.

---

### 2. Supadata API rate limit hit mid-collection

**Problem:** The Supadata API free tier enforces both a monthly limit (100 requests) and a per-minute rate limit. The script's initial 1.3 second delay between requests was too short, causing HTTP 429 errors on 9 of 15 videos in the first run.

**Solution:** Increased the sleep interval progressively from 1.3s → 5s → 15s between requests, and added a file-existence check to skip already-fetched transcripts on retry runs. This prevented wasting credits on videos already collected. Final result: 15/15 transcripts collected across 3 runs.

---

### 3. LinkedIn has no accessible API for post collection

**Problem:** LinkedIn actively blocks all third-party scraping tools and requires authentication to view posts. No free, compliant API exists for collecting post content programmatically.

**Solution:** Each file in `research/linkedin-posts/` is pre-structured with a collection template and a direct link to the expert's activity feed (`linkedin.com/in/{handle}/recent-activity/shares`). Manual copy-paste is the only compliant method. Instructions are embedded inside each file.

---

### 4. Three initial experts had no recent active posts

**Problem:** Matt Barker, Jasmin Alic, and Lara Acosta — all selected based on reputation and follower count — had no recent active LinkedIn posts at time of verification. Including them would have produced empty files with no research value.

**Solution:** Replaced with three verified-active alternatives (Brendan Hufford, Katelyn Bourgoin, Peep Laja), all manually verified before inclusion. The replacement decision was documented in `sources.md` with full reasoning.

---

### 5. Rebase conflict during Git operations

**Problem:** A `git pull --rebase` command mid-session caused a conflict that temporarily appeared to delete tracked files and created divergent branches between local and remote.

**Solution:** Used `git rebase --abort` to cancel the rebase cleanly, then `git push --force` to reset the remote to the correct local state. No files were lost — Git tracks content, not filesystem state.

---

### 6. Target YouTube channel no longer active

**Problem:** Richard van der Blom's channel (@JustConnectingHUB) was no longer active. One of the three selected videos returned HTTP 404 (video not found).

**Solution:** Found a replacement via web search — a guest appearance on another channel (`mymPtjd48KQ` — "How to Get More Visibility & Engagement on LinkedIn in 2025", May 2025). Same expert, same content quality, different host. Updated the video ID in `scripts/fetch-transcripts.js` and re-ran the fetch.

---

## How to continue this research

### Re-run transcript collection
```bash
cd research
node scripts/fetch-transcripts.js
```
Requires: Supadata API key set in `scripts/fetch-transcripts.js`
Free tier: 100 requests/month — sign up at supadata.ai (no credit card)

### Collect LinkedIn posts
1. Open `research/linkedin-posts/{expert}.md`
2. Click the activity feed URL at the top of the file
3. Copy posts using the template provided in the file
4. Push updates:
```bash
git add .
git commit -m "Add posts: {expert name}"
git push
```

---

## Planned playbook structure

Once source material is complete, the playbook will be built across 8 chapters:

| Chapter | Topic | Primary sources |
|---------|-------|-----------------|
| 01 | Positioning before content | April Dunford + Dave Gerhardt |
| 02 | Profile as a landing page | Justin Welsh + Devin Reed |
| 03 | Content pillars and ICP fit | Amanda Natividad + Brendan Hufford |
| 04 | Post formats and hooks | Katelyn Bourgoin + Devin Reed |
| 05 | Algorithm strategy 2025-26 | Richard van der Blom |
| 06 | Zero Click Content | Amanda Natividad + Chris Walker |
| 07 | From engagement to pipeline | Justin Welsh + Devin Reed |
| 08 | Measurement and iteration | Peep Laja + Richard van der Blom |

---

## Tools used

| Tool | Purpose |
|------|---------|
| Cursor IDE | Agent-based file generation and Git operations |
| Claude (Anthropic) | Research agent, expert curation, file generation |
| Supadata API | YouTube transcript extraction (free tier, 100 req/month) |
| GitHub | Version control and public repository hosting |
| LinkedIn (manual) | Post collection via direct activity feed URLs |

---

*Research repository built as part of a technical portfolio for 100Hires.*
*Last updated: 2026-06-14*
