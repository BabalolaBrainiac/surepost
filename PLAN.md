# SUREPOST — AI-Managed Social Media Monetization System
## Complete Operational Plan v2.5 (OpenClaw Local Orchestration)

> **What this is:** A multi-agent AI workflow running locally on your device via **OpenClaw** that manages the brainwork of your Instagram, TikTok, and Twitter/X accounts end-to-end — researching daily, generating content, and readying media for posting.
>
> **What you do:** Run the OpenClaw orchestrator, review the generated folder of finished media and captions (synced via Google Drive), and manually upload/schedule the content across your accounts.
>
> **What the system does:** Deep research, scriptwriting, voiceover generation, image generation, and final video assembly.
>
> **Security:** 100% secure. You never hand over your credentials or OAuth tokens to an external server. You post directly from your own device.

---

## Table of Contents

1. [The Concept](#1-the-concept)
2. [Critical Clarification — How Automation Works](#2-critical-clarification--how-automation-works)
3. [Niche Strategy — Deep Research](#3-niche-strategy--deep-research)
4. [Platform Strategy](#4-platform-strategy)
5. [Revenue Model — Every Stream](#5-revenue-model--every-stream)
6. [Content System](#6-content-system)
7. [Posting Schedule & Frequency](#7-posting-schedule--frequency)
8. [Technical Architecture (OpenClaw)](#8-technical-architecture-openclaw)
9. [OpenClaw Agent System](#9-openclaw-agent-system)
10. [Skill Definitions](#10-skill-definitions)
11. [Daily Operations Loop](#11-daily-operations-loop)
12. [Growth Trajectory & Revenue Projections](#12-growth-trajectory--revenue-projections)
13. [Monetization Activation Timeline](#13-monetization-activation-timeline)
15. [Account Setup Instructions](#15-account-setup-instructions)
17. [Risk & Platform TOS Compliance](#17-risk--platform-tos-compliance)
18. [File Structure](#18-file-structure)

---

## 1. The Concept

SurePost is not a tool you use. It is a system that works for you.

You own three social media accounts. The system manages all three, around the clock. Every day it:

- Scans what is trending on each platform and in your niche
- Analyses competitor accounts and identifies gaps
- Generates content calibrated for maximum reach and engagement
- Posts at the precise moment your audience is most active
- Tracks every metric and feeds outcomes back to improve the next post
- Identifies monetization opportunities and activates them in sequence
- Reports revenue generated to you daily

The accounts build a compounding brand. Every follower gained increases the value of the next post. Every piece of engagement data makes the next recommendation more accurate. Every brand deal unlocked opens the door to larger ones.

The system is autonomous. It does not wait for your input. It operates daily whether or not you are watching.

---

## 2. Critical Clarification — Local Orchestration

### What the system IS

An automated local workflow running via **OpenClaw** — an open-source agent orchestration framework. You run this on your Mac. It is powered by AI models (primarily **Kimi** for content, **Claude** for research/strategy) and a media generation pipeline (getimg.ai and local ffmpeg). The agents defined in this plan run as local processes, directly outputting text and video files to a designated folder (e.g., Google Drive).

### What the system is NOT

A cloud service running 24/7. It does not hit the platform APIs (Instagram/TikTok/Twitter) directly. This eliminates the risk of account bans due to API limits or unofficial scraping, and completely bypasses TikTok's strict 500-follower requirement for API access.

### The Publishing Workflow

Instead of the system posting for you, it prepares a complete **"Daily Delivery Cache"**.
Every day, you run OpenClaw and it deposits a structured folder in your Google Drive:

`/SurePost_Content/2026-03-04/`
- `TikTok_1.mp4`
- `IG_Reel.mp4`
- `IG_Carousel/` (Images)
- `Twitter_Thread.md`
- `Captions_and_Hashtags.txt`

You open the folder on your phone or desktop, review the content, and manually upload. You retain 100% control over your accounts, and server costs drop to exactly $0.

---

## 3. Niche Strategy — Deep Research

### The Selection Framework

The highest-revenue niches share four properties:
1. **High advertiser CPM** — brands pay premium to reach this audience
2. **Platform algorithm favor** — content type matches what the platform wants to surface
3. **Affiliate ecosystem** — multiple high-commission programs exist in the niche
4. **Cross-platform compounding** — audience on one platform converts to follower on another

### Recommended Niche: AI × Money

**Full description:** The intersection of artificial intelligence tools and personal finance/income generation. Content covers: how to use AI to make money, AI tools for passive income, AI-assisted investing, side hustles powered by AI, AI productivity for entrepreneurs.

**Why this niche wins in 2026:**

| Signal | Data Source |
|--------|------|
| Finance/AI TikTok CPM (blended) | $13–$15 per 1,000 views (vs $2–4 for entertainment) |
| Finance content CPM (Instagram brand deals) | $15–$25 per 1,000 impressions |
| AI niche TikTok RPM (Creator Rewards) | $2.00–$8.00 per 1,000 qualified views |
| Affiliate commissions available | 30–60% recurring (SaaS tier 1 programs) |
| Brand deal premium vs lifestyle niche | 2.5–3x higher for same audience size |
| Creator economy AI niche growth | +120% YoY (2025 data) |
| Audience purchasing power | Very high — SaaS buyers spending $50–200/month on tools |
| Competition level | Medium — niche growing faster than quality creators |
| Cross-platform synergy | Very high — same audience on all 3 platforms |

**Why not pure Finance:** Over-saturated, heavily regulated, requires disclaimers
**Why not pure AI:** Less monetizable without the money angle
**Why AI × Money:** The intersection is growing fast, lightly contested, and every AI SaaS tool wants to advertise here

### Alternative Niches (if AI × Money feels off-brand)

| Niche | Platforms | Monthly CPM | Affiliate Ecosystem | Difficulty |
|-------|-----------|------------|--------------------|----|
| AI × Money (recommended) | All 3 | $8-18 | Excellent | Medium |
| Productivity × Minimalism | IG + TT + X | $5-12 | Good | Low |
| Health × Science | IG + TT | $6-14 | Excellent | Medium |
| Business × Entrepreneurship | IG + X | $7-16 | Excellent | High |
| Fitness × Longevity | IG + TT | $5-10 | Excellent | High |

### Niche Research Process (Daily)

Every day at 06:00 UTC, the NICHE_MONITOR_AGENT runs:
1. Scrapes trending topics on each platform for AI + Finance + Productivity keywords
2. Analyses top-performing posts in the niche from the last 24 hours
3. Identifies emerging sub-topics before they peak (early = algorithm favor)
4. Updates the content strategy for the day with trending angles
5. Flags any competitor accounts that are growing faster than benchmarks for gap analysis

---

## 4. Platform Strategy

### Instagram — Visual Authority

**Account type:** Creator Account (required for API posting + insights)
**Content format priority:** Carousels > Reels > Single Image > Stories
**Voice:** Authoritative but accessible. Expert who explains simply.
**Growth lever:** Carousels get shared and saved — the two signals Instagram's algorithm weights heaviest.

**Content pillars:**
- "X AI tools that pay you" (carousels — extremely high save rate)
- "How I made $X using AI this week" (Reels — high reach)
- Behind-the-scenes of AI workflows (Stories — daily touchpoint)
- "AI tool review: worth it or not" (single image + caption — engagement driver)

**Posting frequency:** 1 Reel + 1 Carousel + 3–5 Stories per day
**Optimal times:** Tuesday–Thursday 5–7pm local audience timezone, Friday 12pm

**Monetization on Instagram:**
- Brand deals (primary)
- Affiliate links in bio (Linktree with tracked links)
- Instagram Subscriptions (exclusive content at $0.99–$9.99/mo)
- Digital product sales via link in bio

---

### TikTok — Reach Engine

**Account type:** Business Account (required for Content Posting API)
**Content format priority:** Videos 15–60 seconds, vertical, hook in first 0–2 seconds
**Voice:** Fast, punchy, genuinely useful. No fluff. Every second earns the next.
**Growth lever:** Watch completion rate and shares. The algorithm distributes widely before it distributes deeply.

**Content pillars:**
- "I tried [AI tool] so you don't have to" (demo format — very high completion)
- "How to make money with AI in [time]" (aspirational — high share rate)
- POV: using AI to [task] (immersive format — high completion)
- "The AI tool [big company] doesn't want you to know" (curiosity gap — high engagement)
- Day-in-the-life using AI tools (authenticity — high saves)

**Posting frequency:** 3–4 videos per day
**Optimal times:** 2–4pm, 7–9pm local audience timezone (staggered to avoid self-competition)

**Monetization on TikTok:**
- TikTok Creator Rewards Program (requires 10K followers + 100K views/30 days)
- Brand deals (highest per-view rate after 50K followers)
- Affiliate links in bio
- TikTok Series (paid video content)
- TikTok LIVE (gifts + subscriptions)

---

### Twitter/X — Thought Leadership + Distribution

**Account type:** Standard (API access at basic tier; Pro recommended for analytics)
**Content format priority:** Threads > Single tweets > Spaces
**Voice:** Direct, opinionated, insightful. The person who says what others are thinking.
**Growth lever:** Replies and quote tweets. X rewards conversational accounts.

**Content pillars:**
- Daily "AI tools roundup" thread (7–10 tools with brief take — highly shareable)
- "Hot take" tweets about AI and money (controversial but defensible — huge engagement)
- "I built X using AI in Y minutes" (proof content — high retweets)
- Breaking AI news with personal analysis (real-time relevance — fast reach)
- Financial independence + AI philosophy (builds loyal follower base)

**Posting frequency:** 5–8 tweets/threads per day
**Optimal times:** 8–9am, 12–1pm, 5–7pm (audience skews professional)

**Monetization on Twitter/X:**
- X Premium revenue share (ads in replies — requires 500+ followers + 5M impressions/3 months)
- Subscriptions via X (fan content)
- Newsletter via Substack or X Notes (premium tier)
- Affiliate links in tweets and bio
- Consulting/service leads (X is the best B2B lead gen platform)

---

## 5. Revenue Model — Every Stream

### Revenue Stack by Follower Milestone

**Phase 1: 0 → 10,000 followers (Months 1–3)**
- Affiliate marketing only
- Target programs: AI tool SaaS (20–40% recurring commission), investing apps ($50–$150 CPA)
- Expected monthly revenue: $200–$800

**Phase 2: 10,000 → 50,000 followers (Months 3–6)**
- Affiliate marketing (growing)
- TikTok Creator Rewards Program activates at 10K
- First small brand deals ($100–$500 per post)
- Instagram Subscriptions launch
- Expected monthly revenue: $800–$3,000

**Phase 3: 50,000 → 100,000 followers (Months 6–9)**
- Brand deals scale significantly ($500–$2,500 per post)
- X Premium revenue share activates
- TikTok Creator Fund meaningful
- Affiliate at scale (authority = higher conversion)
- Digital product launch (AI tools guide, $29–$97)
- Expected monthly revenue: $3,000–$10,000

**Phase 4: 100,000+ followers (Month 9+)**
- Premium brand deals ($1,500–$8,000 per post per platform)
- All platform monetization programs active
- Digital product suite
- Potential agency model (managing others with the system)
- Expected monthly revenue: $10,000–$50,000+

### Affiliate Programs to Activate (In Order)

See `AFFILIATE_STACK.md` for the complete program details, content angles, and revenue projections.

| Program | Commission | Cookie | Priority | Why |
|---------|-----------|--------|----------|---------|
| Systeme.io | 60% lifetime recurring | Lifetime | Day 1 | Highest commission rate + lifetime cookie |
| Copy.ai | 45% for 12 months | 60 days | Day 1 | Highest short-term payout |
| Jasper AI | 30% recurring | 30 days | Day 1 | Brand recognition = high conversion |
| HubSpot | 30% for 12 months | 180 days | Day 1 | Longest cookie window in class |
| ActiveCampaign | 30% recurring | 90 days | Week 1 | Email automation angle |
| Semrush | $200/sale | 120 days | Month 1 | High-ticket single sale |
| NordVPN | 40% new + 30% renewal | 30 days | Month 1 | Universal creator tool |
| Beehiiv | $50/subscriber | 30 days | Month 1 | Newsletter platform, premium CPA |
| Canva Pro | $36/annual signup | 30 days | Week 2 | High conversion from free tier |
| Hostinger | 60% commission | 30 days | Month 2 | Highest % in web hosting category |

**Total affiliate potential at 50K followers:** $3,000–$6,000/month (compounding with recurring programs)

**Compound effect:** Recurring commissions from months 1–11 accumulate. By month 12, Systeme.io referrals from month 1 have been paying for 11 months.

---

## 6. Content System

### The Content Engine

Every piece of content follows a research → generate → validate → post → measure loop.

```
06:00 UTC  NICHE_MONITOR_AGENT     → scans trends, updates daily brief
07:00 UTC  CONTENT_STRATEGY_AGENT  → creates day's content plan (angles, hooks, formats)
08:00 UTC  CONTENT_CREATION_AGENT  → generates all content for the day
09:00 UTC  QUALITY_GATE            → validates content (confidence >= 0.90)
09:30 UTC  Human review window     → optional 30-min hold for manual review
10:00 UTC  SCHEDULER_AGENT         → queues posts at optimal platform times
           POSTING_AGENT           → executes posts via APIs throughout day
24h later  ANALYTICS_AGENT         → measures outcomes, updates model
```

### Content Quality Standards

Every post must pass:
- **Hook test:** Does the first line/frame make someone stop scrolling?
- **Value test:** Does this post give the viewer something useful or interesting?
- **Niche fit test:** Is this clearly in the AI × Money niche?
- **Platform native test:** Does this feel native to this specific platform?
- **Confidence threshold:** AI confidence score >= 0.90 before posting

### The Hook Library

The system maintains a continuously updated library of proven hooks, structured by hook type. Refreshed weekly based on what is performing in the niche. Full research analysis in `NICHE_INTELLIGENCE.md`.

**Bold Claim hooks (highest watch-through rate):**
- "I replaced my $500/month software stack with these 5 free AI tools."
- "This AI tool generated $340 in commissions while I slept."
- "Stop paying for [X]. This free AI does it better."
- "I made $[X] last month using only AI tools. Here's exactly how."

**Pattern Interrupt hooks (highest share rate):**
- "The AI side hustle nobody is talking about in 2026."
- "I found the one AI tool that actually pays you back."
- "Everyone is sleeping on this AI income strategy."
- "POV: you just found out AI generates income while you sleep."

**Curiosity Gap hooks (highest completion rate):**
- "The free AI tool that paid creators are hiding from you."
- "I gave AI my expenses and this happened."
- "Nobody told me AI could do this for money."

**Problem-Solution hooks (highest save rate):**
- "Struggling with [pain point]? AI fixed it in 4 minutes."
- "The reason you're not making money with AI yet."
- "I tested 47 AI tools. These 5 actually make money."

**Twitter/X thread hooks:**
- "I've been using AI to [outcome] for 6 months. Here's what I learned: [thread]"
- "Hot take: [controversial but defensible statement about AI pricing or value]"
- "The AI tool landscape just changed. Here's what happened and what to do: [thread]"
- "I made [outcome] this week using only free AI tools. A thread:"

**Hook rotation rule:** Never use the same hook type twice in a row within one platform. Rotate: bold_claim → curiosity_gap → pattern_interrupt → problem_solution → personal_story → repeat.

### Cross-Platform Content Adaptation

One core idea generates 5–7 pieces of content per day:

```
Core insight: "ChatGPT can write a week of social media content in 10 minutes"

→ TikTok:  60s demo video script showing the exact process
→ TikTok:  "3 prompts I use every week" short format
→ Instagram Reel: condensed 15s version with hook optimized for IG
→ Instagram Carousel: 7-slide breakdown of the prompts with examples
→ Instagram Story: poll "do you use AI for content?" + swipe-up
→ Twitter: thread "here's exactly how I prompt ChatGPT for a week of content:"
→ Twitter: hot take "AI content tools will replace social media managers by 2027"
```

This is not spam. Each piece is genuinely adapted for its platform. The TikTok video and the Instagram carousel are completely different executions of the same idea.

---

## 7. Posting Schedule & Frequency

### Daily Post Volume

| Platform | Daily Posts | Format Mix |
|----------|------------|------------|
| TikTok | 3–4 videos | Short demo, POV, list format, trending audio |
| Instagram | 1 Reel + 1 Carousel + 4 Stories | Mix of formats daily |
| Twitter/X | 6–8 posts | 1 thread + 5–7 single tweets |

**Total: 10–13 posts per day across all platforms**

This is high volume by design. The algorithm discovery window is won by consistency. Accounts that post daily compound faster than accounts that post weekly.

### Weekly Content Calendar Structure

| Day | TikTok Focus | Instagram Focus | Twitter/X Focus |
|-----|-------------|-----------------|-----------------|
| Monday | Motivational AI story | Carousel: AI tools list | Thread: weekly AI news |
| Tuesday | Tutorial/demo | Reel: quick tip | Hot takes |
| Wednesday | "I tried X" review | Behind-the-scenes | AMA thread or Q&A |
| Thursday | POV format | Carousel: money angle | Data/stats tweet |
| Friday | Trending audio + AI | Reel: high energy | Roundup thread |
| Saturday | Viral-attempt content | Stories focus | Engagement tweets |
| Sunday | Softer/personal story | Reflection carousel | Planning/productivity |

### Optimal Posting Times (UTC — Research-Validated)

These times are derived from 2025 platform engagement data and calibrated for a US-primary audience. The system auto-adjusts within 4 weeks based on actual account audience timezone data from the platform APIs.

**TikTok (3 posts/day):**
- Post 1: 13:00 UTC (8–9 AM ET) — morning commute / early scroll
- Post 2: 19:00 UTC (2–3 PM ET) — afternoon break
- Post 3: 00:00 UTC (7–8 PM ET) — peak evening

**Instagram Reel:** 22:00 UTC (5–6 PM ET) Monday–Thursday
**Instagram Carousel:** 14:00–16:00 UTC (9–11 AM ET) — peak save rate window
**Instagram Stories:** 16:00, 19:00, 23:00 UTC (3x daily)

**Twitter/X:**
- Thread: 13:00 UTC (9 AM ET) — business hours, highest impressions
- Hot take: 17:00 UTC (1 PM ET) — lunchtime engagement peak
- Reply farming: 13:00–14:00 UTC window (before thread posting)
- Evening tweet: 22:00 UTC (6 PM ET)

**Weekly best days:**
- TikTok: Tue–Thu strongest, post every day regardless
- Instagram: Mon, Tue, Thu strongest for Reels
- Twitter/X: Tue–Thu strongest, Mondays good for weekly threads

See `CONTENT_CALENDAR.md` for the full day-by-day posting schedule.

---

## 8. Technical Architecture (OpenClaw)

```text
┌───────────────────────────────────────────────────────────────┐
│              SUREPOST OPENCLAW ORCHESTRATOR                   │
├───────────────────────────────────────────────────────────────┤
│                                                               │
│  [OpenClaw Runtime]  ← Runs locally on your Mac               │
│         │                                                     │
│  ┌──────┼─────────────────────────────┐                       │
│  ▼      ▼                             ▼                       │
│ [Research Agent]    [Content Agent]   [Media Agent]           │
│  │                  │                 │                       │
│  ▼                  ▼                 ▼                       │
│ [Web/Trend Tools]  [LLM Tools]        [Local Skills]          │
│ Local Scrapers     Kimi (content)     getimg.ai (images)      │
│                    Claude (strategy)  local ffmpeg (video)    │
│                                       ElevenLabs (voiceover)  │
│                   ▼                                           │
│         [Export/Coordinator Agent]                            │
│         Assembles final MP4s, images, and captions into       │
│         a timestamped Google Drive synced folder.             │
│                                                               │
│                   ▼                                           │
│  [You] ← Open Drive folder, manually upload to TikTok/IG/X    │
└───────────────────────────────────────────────────────────────┘
```

### Stack & Budget Breakdown ($0-10/mo)

| Layer | Technology | Provider / Cost |
|-------|-----------|-----|
| Orchestration | **OpenClaw** | Local Mac ($0) |
| Database | Local SQLite / File System | Local ($0) |
| Content Generation | Kimi API (Moonshot AI) | ~$3-5/mo (per token) |
| Strategy & Research | Claude 3.5 Haiku | ~$1-2/mo (per token) |
| Image Generation | getimg.ai (FLUX Schnell) | ~$2-3/mo ($0.003/img) |
| Video Generation | local `ffmpeg` + TTS | Local/Free Tier ($0) |
| Output Sync | Google Drive | Existing ($0) |
| **Total** | | **~$6-10/month** (API usage only) |

---

## 9. OpenClaw Agent System

### Agent Inventory

| Agent | Core AI Model | Role | Runs (UTC) |
|-------|--------------|------|------------|
| PRIME_AGENT | Claude 3.5 Haiku | Orchestrates all agents, tracks milestones | Daily 06:00 |
| NICHE_MONITOR_AGENT | Claude 3.5 Haiku | Deep analysis of trends & competitors | Daily 06:00 |
| ANALYTICS_AGENT | Claude 3.5 Haiku | Pattern recognition on post performance | Daily 06:00 |
| CONTENT_STRATEGY_AGENT | Claude 3.5 Haiku | Selects hooks and angles for the day | Daily 07:00 |
| CONTENT_CREATION_AGENT | Kimi (Moonshot) | Bulk writing of captions, threads, scripts | Daily 08:00 |
| MEDIA_GENERATION_AGENT | Kimi + getimg.ai | Generates image prompts, fetches media, assembles video | Daily 08:30 |
| QUALITY_GATE_AGENT | Kimi (Moonshot) | Validates rules (no emoji, character limits) | Daily 09:00 |
| EXPORT_AGENT | Local Scripts | Organizes content into Google Drive structures | End of Run |

Agents will be defined as OpenClaw agent configurations.

---

## 10. Skill Definitions

| Skill | File | Purpose |
|-------|------|---------|
| trend-scanner | skills/trend-scanner.yaml | Identifies trending topics in niche |
| hook-generator | skills/hook-generator.yaml | Writes scroll-stopping first lines |
| content-writer | skills/content-writer.yaml | Full post content generation |
| platform-formatter | skills/platform-formatter.yaml | Formats content per platform rules |
| optimal-time-calculator | skills/optimal-time-calculator.yaml | Predicts best posting time |
| engagement-predictor | skills/engagement-predictor.yaml | Predicts engagement before posting |
| affiliate-matcher | skills/affiliate-matcher.yaml | Matches content to affiliate programs |
| competitor-scanner | skills/competitor-scanner.yaml | Scans competitor posts and performance |
| revenue-calculator | skills/revenue-calculator.yaml | Tracks and projects revenue |
| post-publisher | skills/post-publisher.yaml | Executes API calls to post content |

Skills will be defined as OpenClaw Tools and Python/Bash local execution scripts.

---

## 11. Daily Operations Loop

### 06:00 UTC — Research Phase

**ANALYTICS_AGENT** (reviews yesterday):
- Pulls metrics from all 3 platforms for yesterday's posts
- Identifies which posts overperformed vs prediction
- Updates content strategy weights (more of what worked)
- Logs accuracy score for each AI prediction

**NICHE_MONITOR_AGENT** (scans today):
- Queries trending topics on each platform
- Monitors top 20 competitor accounts for what they posted and how it performed
- Identifies any breaking news in the AI / money space
- Produces "daily brief" — ranked list of 10 content angles with estimated viral potential

### 07:00 UTC — Strategy Phase

**CONTENT_STRATEGY_AGENT** receives:
- Yesterday's analytics report
- Today's daily brief
- Current follower counts and monetization milestones
- Day of week (content varies by day)
- Any scheduled brand deal content or affiliate pushes

Produces:
- Content plan: 10–13 posts across all platforms
- For each post: platform, format, hook angle, core message, affiliate opportunity, target posting time
- Confidence score per planned post

### 08:00 UTC — Content Creation Phase (Kimi)

**CONTENT_CREATION_AGENT** executes the plan:
- Generates full caption/script for every post (using Kimi `moonshot-v1-32k`).
- Writes 3 hook variations per post (best one selected by predictor).
- Adapts core ideas across platforms (Reels → TikToks → X Threads).
- Writes image prompts for the Media Pipeline.

### 08:30 UTC — Media Generation Phase

**MEDIA_GENERATION_AGENT** executes generation:
- Image generation via `getimg.ai` (FLUX Schnell) for all carousels, X visual posts, and video backdrops.
- Voiceover generation (via ElevenLabs or Kokoro TTS) from Kimi's scripts.
- Video assembly (using in-process `ffmpeg`) to stitch AI images + Text + TTS into vertical 30-60s videos for TikTok and Reels.

### 09:00 UTC — Quality Gate

**QUALITY_GATE_AGENT** reviews every post:
- Media generated successfully? (fallback to pre-rendered generic backgrounds if API failed)
- Platform native? (Twitter content limits, IG image ratios)
- Niche consistent? (AI × Money brand safety)
- Affiliate compliance?

Posts that fail: regenerated automatically (up to 3 attempts), then escalated to human review queue.

### 09:30 UTC — Human Review Window

30-minute window where you can review today's posts at `dashboard.surepost.app`. You can:
- Approve all (default if you do nothing)
- Reject specific posts
- Edit any post
- Pause posting for a day

If you take no action, all approved posts go to scheduler automatically.

### 09:30 UTC — Export & Sync Phase

**EXPORT_AGENT** takes the successfully generated assets and organizes them into a clear folder structure in your Google Drive sync directory.

```
Google Drive/SurePost_Content/
└── 2026-03-04/
    ├── Content_Plan_and_Captions.txt
    ├── TikTok/
    │   ├── Video1_Hook.mp4
    │   ├── Video2_Story.mp4
    │   └── Video3_Trend.mp4
    ├── Instagram/
    │   ├── Reel.mp4
    │   └── Carousel_12/ (Images 1-7)
    └── Twitter/
        └── Thread_Draft.txt
```

### 10:00 UTC (or at your leisure) — Manual Publishing

You open the Google Drive folder on your phone and upload the content to the various platforms. Because the captions, hashtags, and media are 100% completed, the manual effort takes less than 10 minutes per day.

---

## 12. Growth Trajectory & Revenue Projections

### Conservative Model (Research-Calibrated)

| Month | IG Followers | TT Followers | X Followers | Monthly Revenue |
|-------|-------------|-------------|-------------|-----------------|
| 1 | 2,000 | 5,000 | 1,500 | $700 |
| 2 | 8,000 | 18,000 | 5,000 | $2,000 |
| 3 | 22,000 | 45,000 | 14,000 | $5,050 |
| 4 | 40,000 | 90,000 | 25,000 | $9,500 |
| 5 | 65,000 | 145,000 | 38,000 | $14,000 |
| 6 | 100,000 | 210,000 | 55,000 | $20,000 |
| 9 | 180,000 | 380,000 | 100,000 | $45,000 |
| 12 | 280,000 | 600,000 | 180,000 | $80,000+ |

> These projections are more aggressive than previous versions, reflecting the compounding effect of recurring affiliate income (programs like Systeme.io pay lifetime). By month 12, months 1–11 of recurring commissions are stacking.

### Aggressive Model (1+ viral breakout)

| Month | TT Followers | Monthly Revenue |
|-------|-------------|-----------------|
| 2 | 80,000+ | $5,000+ |
| 4 | 300,000+ | $25,000+ |
| 6 | 700,000+ | $70,000+ |

Posting 3–4 videos per day in the AI × money niche is a high-probability path to at least 1 viral video (1M+ views) within the first 3 months. The niche has produced multiple 10M+ view videos in 2025 from zero-follower accounts. Volume + quality = variance reduction.

### Revenue Breakdown at Month 9 ($45,000 target)

| Stream | Platform | Monthly Amount |
|--------|---------|---------------|
| Brand deals | IG + TT | $18,000–$25,000 |
| Affiliate (recurring SaaS stack) | All platforms | $8,000–$12,000 |
| TikTok Creator Rewards | TikTok | $4,000–$8,000 |
| X Premium revenue share | Twitter/X | $1,500–$2,500 |
| Digital product sales | All (link in bio) | $3,000–$6,000 |
| Instagram Subscriptions | Instagram | $1,000–$2,000 |
| Newsletter (Beehiiv) | Email | $500–$2,000 |
| **Total** | | **$36,000–$57,500** |

Key insight: at 100K+ TikTok followers in the AI niche, Creator Rewards alone pays $4,000–$8,000/month. Combined with a SaaS affiliate stack that compounds monthly, $45K is conservative.

---

## 13. Monetization Activation Timeline

### Week 1
- [ ] Accounts created + converted to Creator/Business
- [ ] OAuth tokens connected to system
- [ ] Affiliate links created: Jasper, Copy.ai, Notion, Canva
- [ ] Linktree or Beacons bio page live with tracked links
- [ ] System posting begins

### Month 1
- [ ] Affiliate links in every applicable post
- [ ] First affiliate commissions appearing
- [ ] Analyse which affiliate programs are converting

### Month 2 (at ~5K TikTok followers)
- [ ] Apply for TikTok Creator Rewards Program (requires 10K — aggressively push for it)
- [ ] Begin outreach to small AI tool brands for first paid posts ($100–$300 range)
- [ ] Launch Instagram Subscriptions at $0.99/month (low barrier, builds habit)

### Month 3 (at ~10K TikTok followers)
- [ ] TikTok Creator Rewards Program activated
- [ ] First real brand deals ($200–$600 per post)
- [ ] X Premium revenue share application (needs 500 followers + impression threshold)
- [ ] Digital product development begins (AI tools guide)

### Month 4–5 (at ~30K–50K TikTok followers)
- [ ] Digital product launch ($29–$47 guide)
- [ ] Brand deals increasing ($500–$1,500 per post)
- [ ] Media kit created and distributed to brands in niche
- [ ] Newsletter launched (Beehiiv) — additional revenue stream

### Month 6+ (at ~80K TikTok followers)
- [ ] Premium brand deals ($1,500–$5,000 per post)
- [ ] Sponsorship manager or agency contact considered
- [ ] Course/workshop product ($97–$297)
- [ ] Explore agency model (managing others' accounts with the same system)

---

## 18. File Structure

```
surepost/
├── PLAN.md                          ← this file
├── AGENTS_GUIDE.md                  ← wardscribe.io upload guide
├── agents/
│   ├── PRIME_AGENT.md
│   ├── NICHE_MONITOR_AGENT.md
│   ├── CONTENT_STRATEGY_AGENT.md
│   ├── CONTENT_CREATION_AGENT.md
│   ├── POSTING_AGENT.md
│   ├── ANALYTICS_AGENT.md
│   ├── MONETIZATION_AGENT.md
│   ├── SECURITY_AGENT.md
│   ├── GROWTH_AGENT.md
│   └── QUALITY_GATE_AGENT.md
├── skills/
│   ├── trend-scanner.yaml
│   ├── hook-generator.yaml
│   ├── content-writer.yaml
│   ├── platform-formatter.yaml
│   ├── optimal-time-calculator.yaml
│   ├── engagement-predictor.yaml
│   ├── affiliate-matcher.yaml
│   ├── competitor-scanner.yaml
│   ├── revenue-calculator.yaml
│   └── post-publisher.yaml
├── rules/
│   ├── NO_EMOJI.md
│   ├── SECURITY_ENFORCEMENT.md
│   └── CONTENT_COMPLIANCE.md
└── archive/
    └── (v1 SaaS plan and agents)
```

---

## 19. Media Generation System

Because AI video generation (Sora, Veo) remains expensive and slow in early 2026, SurePost uses an intelligent pre-assembly strategy.

**Video Pipeline Workflow (for TikTok & Reels)**
1. **Script via Kimi**: Kimi generates voiceover script and 5 visual prompts.
2. **Audio via ElevenLabs**: TTS generates a high-quality human-like voiceover file.
3. **Images via getimg.ai**: FLUX Schnell generates 5 high-quality AI images ($0.003 each).
4. **Assembly via FFmpeg**: The Go backend runs local `ffmpeg` (via standard library cmd/exec) to:
   - Apply a slow zoom (Ken Burns effect) to the images.
   - Sync image transitions to the audio length.
   - Overlay subtitles (using custom font generated or bundled with the binary).
5. **Output**: A crisp, 30-45s vertical MP4 specifically formatted for TikTok.

This entire pipeline costs ~$0.02 per video, ensuring maximum output volume without breaking the monthly budget.

---

*SurePost v2.1 — Autonomous Social Media Monetization System*
*Niche: AI × Money | Platforms: Instagram + TikTok + Twitter/X*
*Objective: Maximum revenue through compound follower growth and diversified monetization*
*Reorchestrated: 2026-03-04 (Kimi/media-stack edition)*
