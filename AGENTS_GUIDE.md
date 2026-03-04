# SurePost Agents Guide

version: 2.0.0
last updated: 2026-03-02
system: autonomous social media monetization — ai × money niche

---

## What This System Does

SurePost is an autonomous AI agent system that manages Instagram, TikTok, and Twitter/X accounts for maximum monetization. Every day it:

1. Scans what is trending in the AI × money niche across all platforms
2. Analyses competitor posts and identifies content gaps to exploit
3. Decides what to post, in what format, at what time, on which platform
4. Writes all content — scripts, captions, carousels, threads
5. Checks every post against quality and compliance standards
6. Publishes on the optimal schedule via official platform APIs
7. Tracks revenue across all monetization streams
8. Learns from yesterday's performance to improve today's content

No human input is required for daily operations once accounts are connected and credentials are stored.

---

## System Architecture

```
                    PRIME_AGENT (orchestrator)
                          │
          ┌───────────────┼───────────────┐
          │               │               │
   NICHE_MONITOR    ANALYTICS_AGENT   SECURITY_AGENT
   (06:00 UTC)      (06:00 UTC)       (continuous)
          │
   CONTENT_STRATEGY_AGENT
   (07:00 UTC)
          │
   ┌──────┴──────┐
   │             │
GROWTH_AGENT  MONETIZATION_AGENT
(07:00 UTC)   (08:00 UTC)
          │
   CONTENT_CREATION_AGENT
   (08:00 UTC)
          │
   QUALITY_GATE_AGENT
   (09:00 UTC)
          │
   POSTING_AGENT
   (10:00+ UTC)
```

---

## Agents

### 1. PRIME_AGENT
**File:** `agents/PRIME_AGENT.md`
**Role:** Master orchestrator. Triggers all other agents in sequence. Makes no content decisions itself — its job is coordination, timing, and escalation.
**Runs:** Daily at 06:00 UTC
**Triggers:** NICHE_MONITOR → ANALYTICS → CONTENT_STRATEGY → GROWTH → MONETIZATION → CONTENT_CREATION → QUALITY_GATE → POSTING

---

### 2. NICHE_MONITOR_AGENT
**File:** `agents/NICHE_MONITOR_AGENT.md`
**Role:** Daily intelligence briefing. Scans what is trending in AI, money, side hustle, and creator economy spaces across all three platforms.
**Runs:** 06:00 UTC
**Skills used:** `trend-scanner`, `competitor-scanner`
**Output:** Daily brief — top 10 trending topics with viral potential scores, 5 content gaps identified, competitor activity summary

---

### 3. ANALYTICS_AGENT
**File:** `agents/ANALYTICS_AGENT.md`
**Role:** Reviews yesterday's post performance. Updates the strategy database with what worked and what did not. Adjusts content weights for today.
**Runs:** 06:00 UTC (parallel with NICHE_MONITOR)
**Skills used:** reads platform APIs directly for yesterday's metrics
**Output:** Performance report — engagement rates vs predictions, revenue generated, updated strategy weights

---

### 4. CONTENT_STRATEGY_AGENT
**File:** `agents/CONTENT_STRATEGY_AGENT.md`
**Role:** Decides what to post today. Uses the niche brief and analytics data to build the full content plan — 10–13 posts across all platforms, with topics, formats, affiliate assignments, and posting times.
**Runs:** 07:00 UTC
**Skills used:** `optimal-time-calculator`, `affiliate-matcher`
**Output:** Full content plan for the day

---

### 5. GROWTH_AGENT
**File:** `agents/GROWTH_AGENT.md`
**Role:** Monitors follower growth rate vs targets. If any platform is underperforming its weekly growth target, it adjusts the content strategy for that platform.
**Runs:** 07:00 UTC (parallel with CONTENT_STRATEGY)
**Growth targets:** TikTok +15%/week, Instagram +10%/week, Twitter +12%/week (weeks 1–4)

---

### 6. MONETIZATION_AGENT
**File:** `agents/MONETIZATION_AGENT.md`
**Role:** Tracks all revenue streams and identifies monetization opportunities. Checks if any accounts have just crossed a monetization milestone. Ensures affiliate content is included at the right frequency.
**Runs:** 08:00 UTC
**Skills used:** `revenue-calculator`, `affiliate-matcher`
**Revenue streams tracked:** TikTok Creator Rewards, X Premium revenue share, Instagram Subscriptions, affiliate commissions, brand deal pipeline

---

### 7. CONTENT_CREATION_AGENT
**File:** `agents/CONTENT_CREATION_AGENT.md`
**Role:** Writes all content for the day. Takes each item from the content plan and produces the full post — script + on-screen text for TikTok, slides + caption for Instagram carousels, thread tweets for Twitter. Writes 3 hook variations per post, selects the strongest.
**Runs:** 08:00 UTC
**Skills used:** `hook-generator`, `content-writer`, `platform-formatter`
**Voice rule:** sounds human — direct, expert, slightly informal, short sentences. never AI-sounding.

---

### 8. QUALITY_GATE_AGENT
**File:** `agents/QUALITY_GATE_AGENT.md`
**Role:** Final check before anything is scheduled. Scores every post on 6 criteria. Rejects posts that fail thresholds and triggers regeneration. Compliance must always score 1.0.
**Runs:** 09:00 UTC
**Skills used:** `engagement-predictor`
**Pass thresholds:** hook_strength ≥0.85, platform_native ≥0.90, niche_consistency ≥0.90, value_delivery ≥0.80, compliance 1.0, overall_confidence ≥0.90

---

### 9. POSTING_AGENT
**File:** `agents/POSTING_AGENT.md`
**Role:** Publishes posts at their scheduled times via official platform APIs. Handles media upload, caption formatting, scheduling confirmation. Retries on failure with exponential backoff (max 3 attempts). Alerts on platform pause.
**Runs:** 10:00+ UTC (continuous throughout the day as scheduled post times arrive)
**Skills used:** `post-publisher`
**APIs:** Instagram Graph API v19, TikTok Content Posting API v2, Twitter/X API v2

---

### 10. SECURITY_AGENT
**File:** `agents/SECURITY_AGENT.md`
**Role:** Monitors all platform API activity for anomalies. Manages OAuth token lifecycle — refreshes tokens before expiry, rotates on use, stores encrypted. Pauses operations and alerts on any suspicious pattern.
**Runs:** Continuously (event-driven)
**Token security:** AES-256-GCM encryption, PBKDF2-SHA256 key derivation (100,000 iterations), in-memory decryption only

---

## Skills

| Skill | File | Used By | Purpose |
|---|---|---|---|
| trend-scanner | `skills/trend-scanner.yaml` | NICHE_MONITOR | Scans trending topics, returns viral_potential + trend_stage |
| competitor-scanner | `skills/competitor-scanner.yaml` | NICHE_MONITOR | Scans competitor posts and identifies strategic gaps |
| hook-generator | `skills/hook-generator.yaml` | CONTENT_CREATION | Generates 3 hook variations, selects strongest |
| content-writer | `skills/content-writer.yaml` | CONTENT_CREATION | Writes full post content in all formats |
| platform-formatter | `skills/platform-formatter.yaml` | CONTENT_CREATION | Enforces platform rules (char limits, hashtags, aspect ratios) |
| affiliate-matcher | `skills/affiliate-matcher.yaml` | CONTENT_STRATEGY, MONETIZATION | Matches topic to best affiliate program |
| optimal-time-calculator | `skills/optimal-time-calculator.yaml` | CONTENT_STRATEGY | Predicts best posting time with reach multiplier |
| engagement-predictor | `skills/engagement-predictor.yaml` | QUALITY_GATE | Predicts reach, engagement, revenue before posting |
| post-publisher | `skills/post-publisher.yaml` | POSTING | Executes API posting, returns platform post ID |
| revenue-calculator | `skills/revenue-calculator.yaml` | MONETIZATION | Tracks and projects revenue across all streams |

---

## Rules

| Rule | File | Scope |
|---|---|---|
| No emoji | `rules/NO_EMOJI.md` | All agents, all content |
| Security enforcement | `rules/SECURITY_ENFORCEMENT.md` | SECURITY_AGENT, POSTING_AGENT |
| Content compliance | `rules/CONTENT_COMPLIANCE.md` | All agents — QUALITY_GATE enforces |

---

## File Structure

```
surepost/
├── PLAN.md                          # full system plan and revenue model
├── AGENTS_GUIDE.md                  # this file
├── agents/
│   ├── PRIME_AGENT.md
│   ├── NICHE_MONITOR_AGENT.md
│   ├── ANALYTICS_AGENT.md
│   ├── CONTENT_STRATEGY_AGENT.md
│   ├── GROWTH_AGENT.md
│   ├── MONETIZATION_AGENT.md
│   ├── CONTENT_CREATION_AGENT.md
│   ├── QUALITY_GATE_AGENT.md
│   ├── POSTING_AGENT.md
│   └── SECURITY_AGENT.md
├── skills/
│   ├── trend-scanner.yaml
│   ├── competitor-scanner.yaml
│   ├── hook-generator.yaml
│   ├── content-writer.yaml
│   ├── platform-formatter.yaml
│   ├── affiliate-matcher.yaml
│   ├── optimal-time-calculator.yaml
│   ├── engagement-predictor.yaml
│   ├── post-publisher.yaml
│   └── revenue-calculator.yaml
├── rules/
│   ├── NO_EMOJI.md
│   ├── SECURITY_ENFORCEMENT.md
│   └── CONTENT_COMPLIANCE.md
└── archive/
    └── v1/                          # original saas platform concept
```

---

## LLM Provider Compatibility

Every agent is written in WardPack v1 format and is compatible with 5 LLM providers:

| Provider | Key | Models Used |
|---|---|---|
| Anthropic Claude | `claude` | opus-4-6 (orchestration, security), sonnet-4-6 (content), haiku-4-5 (fast tasks) |
| OpenAI | `openai` | o1 (security reasoning), gpt-4o (content), gpt-4o-mini (fast tasks) |
| Moonshot / Kimi | `moonshot` | moonshot-v1-128k (long context), moonshot-v1-32k (standard), moonshot-v1-8k (fast) |
| Google Gemini | `gemini` | gemini-1.5-pro (deep analysis), gemini-2.0-flash (fast tasks) |
| Cursor | `cursor` | claude-sonnet-4-6 (IDE-integrated, with tool definitions) |

---

## Wardscribe.io Upload Instructions

Each agent file is ready to upload to wardscribe.io as a WardPack v1 agent.

1. Go to wardscribe.io and log in
2. Click "Upload Agent"
3. Select the agent `.md` file from the `agents/` directory
4. Repeat for all 10 agents
5. Upload all 10 skill files from the `skills/` directory as Skill objects
6. Set the pipeline entry point to `PRIME_AGENT`
7. Configure your API keys for whichever LLM providers you are using

Skills are referenced in agent files by name (e.g., `skill: trend-scanner`). wardscribe resolves these automatically when agents and skills are uploaded to the same workspace.

---

## Account Setup Checklist

Before the system can operate, complete these steps:

### Create Accounts
- [ ] Instagram — business account, AI/money niche
- [ ] TikTok — creator account
- [ ] Twitter/X — **aiincome.labs** (upgrade to Premium immediately on Day 1)

### Connect OAuth
- [ ] Instagram: generate access token via Meta Developer Console
- [ ] TikTok: generate access token via TikTok Developer Portal
- [ ] Twitter/X: generate OAuth 2.0 tokens via Twitter Developer Portal
- [ ] Store all tokens in the encrypted credential store (SECURITY_AGENT manages this)

### Affiliate Programs — Apply On Day 1
- [ ] Jasper AI (30% recurring) — jasper.ai/affiliates
- [ ] Copy.ai (45% for 12 months) — copy.ai/affiliates
- [ ] Notion ($10–16 per user) — notion.so/affiliates
- [ ] Canva Pro ($36 per annual sign-up) — canva.com/affiliates
- [ ] Beehiiv ($50 per subscriber) — beehiiv.com/affiliates
- [ ] Hostinger (60% commission) — hostinger.com/affiliates

### Infrastructure
- [ ] Deploy Go backend to Fly.io
- [ ] Set up Temporal Cloud workspace and connect workflows
- [ ] Configure Neon PostgreSQL database
- [ ] Set up Upstash Redis for queues and caching
- [ ] Configure ClickHouse for analytics ingestion
- [ ] Deploy monitoring dashboard to Vercel

---

## Revenue Milestones

| Milestone | Target | Unlocks |
|---|---|---|
| TikTok 10,000 followers | Month 1–2 | TikTok Creator Rewards |
| X 500 followers + Premium | Month 1 | X Premium revenue share |
| Instagram 1,000 followers | Month 1–2 | Instagram Subscriptions |
| TikTok 50,000 followers | Month 2–4 | First digital product launch |
| Instagram 10,000 followers | Month 2–4 | Instagram affiliate link in story |
| All platforms 100K+ | Month 6+ | Inbound brand deals $500–$5,000/post |

**Month 12 projection (conservative):** $45,000/month
- Instagram 150K followers: brand deals + subscriptions + affiliate
- TikTok 280K followers: Creator Rewards + brand deals + affiliate
- Twitter/X 80K followers: Premium revenue share + affiliate
