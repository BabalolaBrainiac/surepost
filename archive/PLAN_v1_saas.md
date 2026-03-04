# SUREPOST - AI-Powered Social Media Optimization Platform
## Complete End-to-End Implementation Plan v1.0

> **Certainty Target:** 95%+ confidence on all AI recommendations
> **Powered by:** Kimi AI (Moonshot) + Multi-Agent Architecture
> **Registry:** wardscribe.io (WardPack v1 format)
> **Security:** Non-negotiable. Dedicated security agent enforces all policies.

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Product Vision & Positioning](#2-product-vision--positioning)
3. [App Naming & Domain Strategy](#3-app-naming--domain-strategy)
4. [System Architecture Overview](#4-system-architecture-overview)
5. [Kimi AI Integration Strategy](#5-kimi-ai-integration-strategy)
6. [Social Media API Integrations](#6-social-media-api-integrations)
7. [AI/ML System Design](#7-aiml-system-design)
8. [Mobile Application (React Native + Expo)](#8-mobile-application-react-native--expo)
9. [Backend Architecture (Go)](#9-backend-architecture-go)
10. [Database Schema](#10-database-schema)
11. [Security Architecture](#11-security-architecture)
12. [Agent Configurations (WardPack v1)](#12-agent-configurations-wardpack-v1)
13. [Skill Definitions (WardPack v1)](#13-skill-definitions-wardpack-v1)
14. [Revenue Model & Pricing](#14-revenue-model--pricing)
15. [Sales Strategy](#15-sales-strategy)
16. [Marketing & Advertising Plan](#16-marketing--advertising-plan)
17. [Go-to-Market Launch Strategy](#17-go-to-market-launch-strategy)
18. [Development Roadmap (Phased)](#18-development-roadmap-phased)
19. [Infrastructure & DevOps](#19-infrastructure--devops)
20. [Monitoring & Observability](#20-monitoring--observability)
21. [Risk Assessment & Mitigation](#21-risk-assessment--mitigation)
22. [File Structure Reference](#22-file-structure-reference)

---

## 1. Executive Summary

SurePost is an AI-powered social media optimization platform that analyzes user profiles across Facebook, Instagram, Twitter/X, TikTok, and YouTube, then delivers precision recommendations - what to post, when to post, which hashtags to use, what content style to adopt - with 95%+ confidence scores.

Powered by Kimi AI (Moonshot), the platform uses a multi-agent system orchestrated through wardscribe.io to continuously learn from platform signals, audience behavior, historical performance, competitor analysis, and trending content to serve each user a personalized, perpetually-updated social media growth engine.

**Core differentiation:** Unlike Hootsuite or Buffer (scheduling tools), SurePost is an intelligence layer. It doesn't just schedule - it tells you exactly what to post, crafts the post, proves why, and tracks the outcome to improve next time.

---

## 2. Product Vision & Positioning

### Vision
Become the de facto AI co-pilot for social media creators, brands, and businesses - the tool that makes professional-grade social media strategy accessible to everyone.

### Target Segments
| Segment | Pain Point | Willingness to Pay |
|---------|-----------|-------------------|
| Individual creators (50K-500K followers) | No time to analyze what works | $29-79/mo |
| Small businesses (1-50 employees) | No social media expertise | $79-199/mo |
| Marketing agencies | Managing 10-100+ accounts | $299-999/mo |
| Enterprise brands | Consistency + analytics at scale | Custom |

### Core Features
- **Profile Audit** - Deep analysis of current social presence, gaps, and opportunities
- **Smart Post Generator** - AI writes platform-native content matched to user voice
- **Optimal Schedule** - Predicts best posting times per platform per user audience
- **Hashtag Intelligence** - Dynamic hashtag scoring and recommendation
- **Monthly Content Calendar** - 30-day pre-planned content with full AI justification
- **Real-time Trend Integration** - Surfaces relevant trending topics to hijack
- **Cross-Platform Adapter** - One idea, auto-adapted for each platform's format
- **Performance Tracker** - Closed loop: measures what worked, retrains predictions
- **Competitor Intelligence** - Monitors and benchmarks against similar accounts
- **SEO/Discovery Optimizer** - Captions, descriptions, alt-text for maximum discoverability

---

## 3. App Naming & Domain Strategy

### Recommended Name: **SurePost**
- **surepost.app** (primary - grab immediately)
- **surepost.io** (backup)
- **getsurepost.com** (fallback)

**Why SurePost wins:**
- "Sure" directly encodes the 95% certainty guarantee into the brand
- "Post" is clear, no explanation needed
- Two syllables, easy recall
- Domain availability window is narrow - secure within 24 hours

### Alternative Names (in priority order)
| Name | Domain | Score |
|------|--------|-------|
| SurePost | surepost.app | 9.5/10 |
| PostIQ | postiq.app | 8.5/10 |
| Rippl | rippl.app | 8/10 |
| Flare | getflare.app | 7.5/10 |
| Pinnacle | pinnacle.social | 7/10 |

### Brand Identity
- **Tone:** Confident, data-driven, precise - no fluff
- **Colors:** Deep navy (#0A1628) + Electric teal (#00D4FF) + Pure white
- **Typography:** Inter (UI) + JetBrains Mono (data/scores)
- **Logo concept:** Stylized upward arrow with a checkmark - certainty + growth

---

## 4. System Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    SUREPOST ARCHITECTURE                    │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  [Mobile App]          [Web Dashboard]                      │
│  React Native          Next.js 15                           │
│  iOS + Android         TypeScript                           │
│       │                     │                               │
│       └──────────┬──────────┘                               │
│                  │ HTTPS / REST + WebSockets                 │
│                  ▼                                           │
│         [API Gateway]                                        │
│         Go 1.23 + Gin                                        │
│         Rate limiting, JWT auth, CORS                        │
│                  │                                           │
│    ┌─────────────┼──────────────┐                           │
│    ▼             ▼              ▼                            │
│ [Auth Service] [Core API]  [AI Orchestrator]                │
│ OAuth 2.0      Go handlers  Multi-Agent System               │
│ JWT + Refresh  PostgreSQL   Kimi AI (Moonshot)               │
│                Redis cache  WardPack Agents                  │
│    │             │              │                            │
│    ▼             ▼              ▼                            │
│ [Social OAuth] [Database]  [Kimi AI API]                    │
│ FB/IG/TW/TT/YT PostgreSQL  moonshot-v1-128k                 │
│ Token vault    Neon         Function calling                 │
│                             Vector store                     │
│                  │                                           │
│         [Message Queue]                                      │
│         Redis + BullMQ                                       │
│         Async job processing                                 │
│                  │                                           │
│    ┌─────────────┼──────────────┐                           │
│    ▼             ▼              ▼                            │
│ [Scheduler]  [Data Pipeline] [ML Pipeline]                   │
│ Post timing  SM API ingestion Model training                 │
│ Temporal     Raw metrics     Fine-tuning loop               │
│              ClickHouse       Model versioning               │
│                                                              │
│  [Storage: Cloudflare R2]  [Search: MeiliSearch]             │
│  [Monitoring: OpenTelemetry + Sentry]                        │
└─────────────────────────────────────────────────────────────┘
```

### Technology Stack Summary

| Layer | Technology | Justification |
|-------|-----------|---------------|
| Mobile | React Native + Expo | Single codebase, iOS + Android, fast iteration |
| Web | Next.js 15 | SSR, SEO, TypeScript, app router |
| Backend | Go 1.23 + Gin | High performance, low memory, concurrency |
| Database | PostgreSQL 15 (Neon) | ACID, JSONB, serverless scaling |
| Cache | Redis (Upstash) | Session, rate limiting, job queues |
| AI | Kimi AI moonshot-v1-128k | Long context, multimodal, function calling |
| Queue | BullMQ + Redis | Reliable async processing |
| Storage | Cloudflare R2 | S3-compatible, zero egress fees |
| Search | MeiliSearch | Full-text search, typo tolerance |
| Workflows | Temporal | Durable, distributed job orchestration |
| Auth | JWT + Clerk OAuth | Social OAuth integration |
| IaC | Terraform | Reproducible infrastructure |
| Deploy | Fly.io (API) + Vercel (Web) + EAS (Mobile) | Zero-downtime, auto-scale |
| Monitoring | OpenTelemetry + Sentry | Distributed tracing + error tracking |
| Analytics | ClickHouse | Time-series, SM metrics, model training data |

---

## 5. Kimi AI Integration Strategy

### Why Kimi AI (Moonshot)
- 128k token context window - can analyze full account history in single prompt
- Multimodal: analyzes images and videos for visual content scoring
- OpenAI-compatible API - easy integration, standard tooling
- Function calling for structured, reliable outputs
- Competitive pricing vs GPT-4o for high-volume inference
- Strong performance on analytical tasks and structured generation

### API Configuration
```
Base URL: https://api.moonshot.cn/v1
Primary Model: moonshot-v1-128k (deep analysis, monthly planning)
Fast Model: moonshot-v1-8k (real-time suggestions, quick scores)
```

### Model Usage Matrix

| Task | Model | Max Tokens | Temperature | Notes |
|------|-------|-----------|-------------|-------|
| Profile deep audit | moonshot-v1-128k | 4096 out | 0.1 | Deterministic analysis |
| Monthly calendar | moonshot-v1-128k | 8192 out | 0.3 | Creative but data-driven |
| Single post generation | moonshot-v1-32k | 2048 out | 0.4 | Platform-native voice |
| Hashtag scoring | moonshot-v1-8k | 512 out | 0.0 | Pure scoring, no creativity |
| Best time prediction | moonshot-v1-8k | 256 out | 0.0 | Deterministic calculation |
| Trend integration | moonshot-v1-32k | 1024 out | 0.5 | Creative + relevant |
| Competitor analysis | moonshot-v1-128k | 4096 out | 0.1 | Full context analysis |

### Function Calling Schema (Critical for 95% certainty)
All AI outputs MUST return structured JSON via function calling - never free text:

```json
{
  "name": "return_post_recommendation",
  "parameters": {
    "type": "object",
    "required": ["post_content", "platform", "confidence_score", "reasoning", "optimal_time", "hashtags"],
    "properties": {
      "post_content": { "type": "string" },
      "platform": { "type": "string", "enum": ["facebook", "instagram", "twitter", "tiktok", "youtube"] },
      "confidence_score": { "type": "number", "minimum": 0, "maximum": 1 },
      "reasoning": { "type": "object" },
      "optimal_time": { "type": "string", "format": "datetime" },
      "hashtags": { "type": "array", "items": { "type": "string" } },
      "predicted_engagement_rate": { "type": "number" },
      "predicted_reach": { "type": "integer" }
    }
  }
}
```

### Confidence Score Architecture
The 95% certainty is achieved through a multi-signal ensemble:

```
Confidence = weighted_average([
  historical_performance_score    * 0.30,  // user's own past data
  platform_algorithm_signal       * 0.25,  // known platform ranking factors
  audience_behavior_pattern       * 0.20,  // when audience is active
  content_type_affinity           * 0.15,  // what content type performs for this niche
  trend_alignment_score           * 0.10   // relevance to current trends
])
```

Recommendations are only served to users when confidence >= 0.80. Above 0.95 is labeled "High Confidence".

### Kimi AI Agent System Prompt Architecture
Each specialized agent gets a tailored system prompt injected into every Kimi call:

```
[AGENT IDENTITY] + [PLATFORM CONTEXT] + [USER PROFILE DATA] + [HISTORICAL METRICS] + [CURRENT TRENDS] + [TASK INSTRUCTION]
```

This fills the 128k context window with maximum signal, enabling precise, personalized recommendations.

---

## 6. Social Media API Integrations

### Platform Coverage Matrix

| Platform | API | Auth | Post | Analytics | Schedule | Webhook |
|----------|-----|------|------|-----------|----------|---------|
| Facebook | Graph API v19 | OAuth 2.0 | yes | yes | yes | yes |
| Instagram | Graph API v19 | OAuth 2.0 | yes | yes | yes | yes |
| Twitter/X | API v2 | OAuth 2.0 + Bearer | yes | yes (Pro) | yes | yes |
| TikTok | Developer API v2 | OAuth 2.0 | yes | yes | yes | no |
| YouTube | Data API v3 | OAuth 2.0 | yes | yes | yes | no |

### Facebook & Instagram (Meta Graph API)

**Required Permissions:**
- `pages_manage_posts` - Post to Pages
- `pages_read_engagement` - Read insights
- `instagram_basic` - Profile access
- `instagram_content_publish` - Publish content
- `instagram_manage_insights` - Analytics
- `instagram_manage_comments` - Comment management

**Key Metrics Available:**
- Reach, Impressions, Engagement rate, Saves, Shares
- Story views, Reel plays, Profile visits
- Follower demographics (age, gender, location, active times)
- Best-performing content by type (image vs video vs carousel vs reel)
- Hashtag performance (Instagram only)

**Data Collection Cadence:**
- Hourly: Basic engagement metrics
- Daily: Full insights refresh (after 24h post window)
- Weekly: Audience demographic updates
- Monthly: Long-term trend analysis

### Twitter/X API v2

**Required Tier:** Pro ($100/mo minimum for analytics)

**Endpoints Used:**
- `POST /2/tweets` - Create tweets
- `GET /2/tweets/:id/metrics` - Engagement metrics
- `GET /2/users/:id/tweets` - Timeline analysis
- `GET /2/trends/by/woeid` - Trending topics
- `GET /2/users/:id` - Profile analytics

**Key Metrics:** Impressions, engagements, link clicks, retweets, quote tweets, replies, profile visits from tweet

### TikTok Developer API v2

**Required:** TikTok for Business account

**Endpoints Used:**
- `POST /v2/post/publish/video/init/` - Video upload
- `GET /v2/research/video/query/` - Video analytics
- `GET /v2/research/user/info/` - Creator analytics
- `GET /v2/research/video/comment/list/` - Comment analysis

**Key Metrics:** Views, likes, comments, shares, watch time, completion rate, profile visits, follower growth from video

### YouTube Data API v3

**Quota:** 10,000 units/day (free tier)

**Endpoints Used:**
- `channels.list` - Channel analytics
- `videos.insert` - Video upload
- `videos.update` - Update metadata/descriptions
- `videoAnalytics.query` - Performance metrics
- `search.list` - Trending/keyword research

**Key Metrics:** Views, watch time, subscriber gain/loss, CTR, average view duration, impressions, card click rate

### OAuth Token Management
ALL social media OAuth tokens are encrypted at rest using AES-256-GCM. Refresh tokens are stored separately in a hardware-isolated vault. See Security Architecture section.

---

## 7. AI/ML System Design

### Core ML Models

#### Model 1: Best Time Predictor (BTP)
**Input features:**
- User's historical post times vs engagement correlation (per platform)
- Follower timezone distribution (from platform API)
- Follower active hours heatmap (7-day rolling)
- Day-of-week performance matrix
- Platform-wide peak times (global + niche-specific)
- Content type (video vs image vs text - different peak patterns)

**Output:** Ranked list of time slots with predicted engagement multiplier

**Training approach:**
- Collect 90 days of post history + engagement data per user
- Time-series feature engineering: rolling averages, lag features, cyclical encoding
- Gradient boosted tree (XGBoost) - interpretable, fast inference
- Continuous retraining as new post data arrives (weekly retrain minimum)
- Cold start: use platform-global + niche benchmarks until 30 posts collected

#### Model 2: Engagement Rate Predictor (ERP)
**Input features:**
- Post text sentiment score and length
- Visual content type (selfie, product, lifestyle, infographic, etc.)
- Hashtag relevance scores + hashtag competition scores
- Caption structure (question, CTA, story, list)
- Historical performance of similar content by same creator
- Platform trend alignment score
- Posting time slot quality score (from BTP)
- Audience activity score at posting time

**Output:** Predicted engagement rate ± confidence interval

**Training approach:**
- Fine-tune on labeled post data (post features → final engagement rate)
- Regression model with uncertainty quantification
- Platform-specific models (separate model per platform)
- User-specific calibration layer on top of base model

#### Model 3: Hashtag Recommendation Engine (HRE)
**Algorithm:**
1. Semantic embedding of post content using Kimi AI embeddings
2. Vector similarity search against hashtag corpus (50M+ hashtags with metrics)
3. Filter by: competition score, growth trajectory, audience overlap
4. Rank by predicted reach-to-competition ratio

**Hashtag tiers (per post):**
- 1-2 mega hashtags (1M+ posts): Broad reach, low per-post visibility
- 3-5 mid hashtags (100K-1M posts): Balanced reach + discoverability
- 5-10 micro hashtags (10K-100K posts): High conversion, niche audience
- 2-3 brand/niche hashtags: Community building

#### Model 4: Content Style Classifier (CSC)
Analyzes a creator's existing content to profile:
- Tone (professional, casual, humor, inspirational, educational)
- Visual style (minimal, vibrant, dark, lifestyle, professional)
- Content formats that resonate (carousels > reels > single images, etc.)
- Caption patterns (emoji usage, question frequency, CTA type)
- Posting personality score

This profile ensures all AI-generated content is indistinguishable from the user's own voice.

#### Model 5: Trend Relevance Scorer (TRS)
- Real-time ingestion of trending topics from each platform API
- Semantic match against user's niche and content history
- Relevance score: is this trend on-brand for this creator?
- Opportunity score: how much engagement uplift can this trend provide?
- Risk score: potential for brand damage if trend is controversial

#### Model 6: Competitor Benchmark Analyzer (CBA)
- Identifies top 5-10 competitors in user's niche (by follower count, engagement)
- Analyzes competitor posting patterns, content types, hashtag strategy
- Extracts what's working for competitors but user hasn't tried
- Provides gap analysis: under-served content formats in niche

### Training Data Pipeline

```
Social Media APIs ──► Raw Metrics Store (ClickHouse)
                              │
                    Feature Engineering Layer
                              │
                    Training Dataset Builder
                              │
              ┌───────────────┼───────────────┐
              ▼               ▼               ▼
         BTP Model       ERP Model       HRE Model
         (XGBoost)       (LightGBM)    (Vector DB)
              │               │               │
              └───────────────┼───────────────┘
                              │
                    Model Registry (versioned)
                              │
                    Inference API (Go wrapper)
                              │
                    Kimi AI Orchestration Layer
                              │
                    Final Recommendation (95%+ confidence)
```

### Closed-Loop Learning
Every recommendation made → user acts (or ignores) → outcome measured → fed back into training data. The system gets smarter with every post made by every user.

---

## 8. Mobile Application (React Native + Expo)

### Stack
- **Framework:** React Native 0.74+ with Expo SDK 51+
- **Navigation:** Expo Router (file-based, web-compatible)
- **State Management:** Zustand (lightweight, < 1KB)
- **API Client:** TanStack Query v5 (React Query)
- **Forms:** React Hook Form + Zod validation
- **UI Components:** NativeWind (Tailwind for React Native) + custom design system
- **Push Notifications:** Expo Notifications (APNs + FCM)
- **Storage:** Expo SecureStore (encrypted local storage)
- **Biometrics:** Expo LocalAuthentication
- **Analytics:** PostHog (self-hosted option available)
- **Crash Reporting:** Sentry
- **Build:** Expo EAS Build + EAS Submit (App Store + Play Store)

### App Structure
```
surepost-mobile/
├── app/
│   ├── (auth)/
│   │   ├── login.tsx
│   │   ├── register.tsx
│   │   └── forgot-password.tsx
│   ├── (onboarding)/
│   │   ├── connect-accounts.tsx
│   │   ├── profile-setup.tsx
│   │   └── goals.tsx
│   ├── (tabs)/
│   │   ├── dashboard.tsx          # Main feed + quick stats
│   │   ├── recommendations.tsx    # AI recommendations list
│   │   ├── calendar.tsx           # Monthly content calendar
│   │   ├── analytics.tsx          # Performance dashboard
│   │   └── settings.tsx
│   ├── post/
│   │   ├── [id].tsx               # Post detail + AI analysis
│   │   ├── create.tsx             # AI-assisted post creation
│   │   └── schedule.tsx           # Schedule a post
│   ├── accounts/
│   │   ├── connect/[platform].tsx # Platform OAuth flow
│   │   └── manage.tsx
│   └── _layout.tsx
├── components/
│   ├── ui/                        # Design system components
│   ├── post/                      # Post-related components
│   ├── analytics/                 # Chart components
│   └── ai/                        # AI recommendation components
├── hooks/
├── lib/
│   ├── api/                       # API client functions
│   ├── auth/                      # Auth utilities
│   └── utils/
├── store/                         # Zustand stores
└── constants/
```

### Key Screens

**Dashboard:**
- Today's recommended post time slot (with confidence score)
- Next 3 content recommendations
- This week's performance snapshot
- Trending topics relevant to user's niche

**Recommendation Detail Screen:**
- Full AI-generated post content
- Platform-specific version (swipe between Facebook/IG/TW etc.)
- Confidence score with breakdown (pie chart of signal weights)
- Predicted engagement range
- Optimal time slot with audience activity heatmap
- Hashtag list with individual scores
- One-tap "Schedule" or "Edit & Schedule"

**Content Calendar:**
- 30-day view with pre-planned posts
- AI-generated content for each day
- Confidence scores per post
- Drag to reschedule
- Export to CSV

**Analytics:**
- Engagement rate trend (actual vs AI prediction)
- Best performing posts with AI accuracy score
- Audience growth chart
- Platform comparison

### Performance Requirements
- App launch: < 1.5 seconds
- API response rendered: < 800ms
- Recommendation generation: < 3 seconds (with loading state)
- Offline support: last 7 days of recommendations cached
- Bundle size: < 25MB iOS, < 30MB Android

---

## 9. Backend Architecture (Go)

### Service Structure
```
surepost-api/
├── cmd/
│   └── server/
│       └── main.go
├── internal/
│   ├── api/
│   │   ├── handlers/
│   │   │   ├── auth.go
│   │   │   ├── accounts.go          # Social media account management
│   │   │   ├── recommendations.go   # AI recommendation endpoints
│   │   │   ├── posts.go             # Post creation + scheduling
│   │   │   ├── analytics.go         # Performance data
│   │   │   ├── calendar.go          # Content calendar
│   │   │   ├── billing.go           # Subscription management
│   │   │   └── webhooks.go          # Platform webhooks
│   │   ├── middleware/
│   │   │   ├── auth.go              # JWT validation
│   │   │   ├── rate_limit.go        # Per-user rate limiting
│   │   │   ├── security.go          # Security headers, CORS
│   │   │   └── logger.go
│   │   └── router.go
│   ├── domain/
│   │   ├── user.go
│   │   ├── social_account.go        # Connected SM accounts
│   │   ├── recommendation.go        # AI recommendation model
│   │   ├── post.go                  # Scheduled/published posts
│   │   ├── analytics.go             # Performance metrics
│   │   ├── subscription.go          # Billing domain
│   │   └── content_calendar.go
│   ├── services/
│   │   ├── ai/
│   │   │   ├── kimi_client.go       # Kimi AI API wrapper
│   │   │   ├── orchestrator.go      # Multi-agent orchestration
│   │   │   ├── recommendation_svc.go
│   │   │   └── confidence_calc.go
│   │   ├── social/
│   │   │   ├── facebook.go          # Facebook/Instagram client
│   │   │   ├── twitter.go           # Twitter/X client
│   │   │   ├── tiktok.go            # TikTok client
│   │   │   ├── youtube.go           # YouTube client
│   │   │   └── token_manager.go     # OAuth token lifecycle
│   │   ├── scheduler/
│   │   │   ├── post_scheduler.go    # Temporal-based post scheduling
│   │   │   └── optimal_time.go
│   │   └── billing/
│   │       └── stripe_service.go
│   ├── repository/
│   │   └── postgres/
│   │       ├── users.go
│   │       ├── social_accounts.go
│   │       ├── recommendations.go
│   │       ├── posts.go
│   │       └── analytics.go
│   ├── jobs/                        # Background jobs (BullMQ-style via Temporal)
│   │   ├── sync_metrics.go          # Pull platform metrics
│   │   ├── generate_recommendations.go
│   │   ├── publish_post.go
│   │   └── retrain_model.go
│   └── config/
│       └── config.go
├── pkg/
│   ├── crypto/                      # AES-256-GCM token encryption
│   ├── jwt/                         # JWT generation/validation
│   └── validator/
├── migrations/
└── configs/
    └── config.yaml
```

### API Endpoints

```
POST   /api/v1/auth/register
POST   /api/v1/auth/login
POST   /api/v1/auth/refresh
DELETE /api/v1/auth/logout

GET    /api/v1/accounts                      # List connected SM accounts
POST   /api/v1/accounts/connect/:platform    # Initiate OAuth flow
DELETE /api/v1/accounts/:id                  # Disconnect account

GET    /api/v1/recommendations               # Get latest AI recommendations
GET    /api/v1/recommendations/:id           # Get recommendation detail
POST   /api/v1/recommendations/generate      # Force regenerate recommendations
POST   /api/v1/recommendations/:id/feedback  # Record user action (used/ignored)

GET    /api/v1/calendar                      # Get monthly content calendar
POST   /api/v1/calendar/generate             # Generate 30-day AI calendar
PUT    /api/v1/calendar/:day                 # Update a calendar day

GET    /api/v1/posts                         # List scheduled/published posts
POST   /api/v1/posts                         # Schedule a post
PUT    /api/v1/posts/:id                     # Update scheduled post
DELETE /api/v1/posts/:id                     # Cancel scheduled post
GET    /api/v1/posts/:id/performance         # Post analytics

GET    /api/v1/analytics/overview            # Account performance summary
GET    /api/v1/analytics/:platform           # Per-platform analytics
GET    /api/v1/analytics/predictions         # Prediction accuracy metrics

GET    /api/v1/trends                        # Current trending topics for user niche

POST   /api/v1/billing/subscribe             # Start subscription
GET    /api/v1/billing/portal                # Stripe portal link
POST   /api/v1/webhooks/stripe               # Stripe webhook handler
POST   /api/v1/webhooks/:platform            # Platform data webhooks
```

---

## 10. Database Schema

### Core Tables

```sql
-- users
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    email VARCHAR(255) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    full_name VARCHAR(255),
    avatar_url VARCHAR(500),
    subscription_tier VARCHAR(50) DEFAULT 'free',
    onboarding_completed BOOLEAN DEFAULT false,
    niche VARCHAR(100),
    goals JSONB,
    created_at TIMESTAMPTZ DEFAULT now(),
    updated_at TIMESTAMPTZ DEFAULT now()
);

-- social_accounts
CREATE TABLE social_accounts (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    platform VARCHAR(50) NOT NULL, -- facebook, instagram, twitter, tiktok, youtube
    platform_user_id VARCHAR(255) NOT NULL,
    platform_username VARCHAR(255),
    access_token_encrypted BYTEA NOT NULL,    -- AES-256-GCM encrypted
    refresh_token_encrypted BYTEA NOT NULL,   -- AES-256-GCM encrypted
    token_expires_at TIMESTAMPTZ,
    scopes TEXT[],
    followers_count INTEGER,
    following_count INTEGER,
    posts_count INTEGER,
    engagement_rate DECIMAL(5,4),
    profile_data JSONB,
    last_synced_at TIMESTAMPTZ,
    is_active BOOLEAN DEFAULT true,
    created_at TIMESTAMPTZ DEFAULT now(),
    UNIQUE(user_id, platform, platform_user_id)
);

-- recommendations
CREATE TABLE recommendations (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    social_account_id UUID REFERENCES social_accounts(id),
    platform VARCHAR(50) NOT NULL,
    post_content TEXT NOT NULL,
    post_content_variants JSONB,  -- per-platform adaptations
    confidence_score DECIMAL(3,2) NOT NULL,
    confidence_breakdown JSONB,   -- signal weights
    optimal_post_time TIMESTAMPTZ NOT NULL,
    hashtags TEXT[],
    hashtag_scores JSONB,
    predicted_engagement_rate DECIMAL(5,4),
    predicted_reach INTEGER,
    reasoning JSONB,
    model_version VARCHAR(50),
    status VARCHAR(50) DEFAULT 'pending', -- pending, scheduled, published, dismissed
    user_action VARCHAR(50),              -- used_as_is, edited, dismissed
    actual_engagement_rate DECIMAL(5,4),  -- filled after publishing
    actual_reach INTEGER,
    prediction_accuracy DECIMAL(3,2),
    expires_at TIMESTAMPTZ,
    created_at TIMESTAMPTZ DEFAULT now()
);

-- content_calendars
CREATE TABLE content_calendars (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    month INTEGER NOT NULL,
    year INTEGER NOT NULL,
    platform VARCHAR(50) NOT NULL,
    calendar_data JSONB NOT NULL,   -- array of 30 daily recommendations
    generation_model VARCHAR(50),
    avg_confidence_score DECIMAL(3,2),
    status VARCHAR(50) DEFAULT 'draft',
    created_at TIMESTAMPTZ DEFAULT now(),
    UNIQUE(user_id, month, year, platform)
);

-- scheduled_posts
CREATE TABLE scheduled_posts (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    social_account_id UUID NOT NULL REFERENCES social_accounts(id),
    recommendation_id UUID REFERENCES recommendations(id),
    platform VARCHAR(50) NOT NULL,
    content TEXT NOT NULL,
    media_urls TEXT[],
    hashtags TEXT[],
    scheduled_for TIMESTAMPTZ NOT NULL,
    status VARCHAR(50) DEFAULT 'scheduled', -- scheduled, published, failed, cancelled
    platform_post_id VARCHAR(255),  -- ID from platform after publishing
    published_at TIMESTAMPTZ,
    error_message TEXT,
    created_at TIMESTAMPTZ DEFAULT now()
);

-- post_analytics
CREATE TABLE post_analytics (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    scheduled_post_id UUID REFERENCES scheduled_posts(id),
    social_account_id UUID NOT NULL REFERENCES social_accounts(id),
    platform VARCHAR(50) NOT NULL,
    platform_post_id VARCHAR(255) NOT NULL,
    metrics JSONB NOT NULL,   -- platform-specific raw metrics
    engagement_rate DECIMAL(5,4),
    reach INTEGER,
    impressions INTEGER,
    likes INTEGER,
    comments INTEGER,
    shares INTEGER,
    saves INTEGER,
    clicks INTEGER,
    recorded_at TIMESTAMPTZ NOT NULL,
    created_at TIMESTAMPTZ DEFAULT now()
);

-- user_audience_profiles
CREATE TABLE user_audience_profiles (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    social_account_id UUID NOT NULL REFERENCES social_accounts(id) UNIQUE,
    active_hours JSONB,      -- hourly activity heatmap (0-23 x 0-6)
    demographics JSONB,      -- age, gender, location breakdown
    interests TEXT[],
    peak_engagement_times JSONB, -- top 5 posting time slots
    content_preferences JSONB,   -- what content performs best
    updated_at TIMESTAMPTZ DEFAULT now()
);

-- training_events (closed-loop ML feedback)
CREATE TABLE training_events (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id),
    event_type VARCHAR(100) NOT NULL,  -- recommendation_generated, post_published, metrics_collected
    features JSONB NOT NULL,           -- input features used
    prediction JSONB,                  -- what model predicted
    outcome JSONB,                     -- what actually happened
    model_version VARCHAR(50),
    created_at TIMESTAMPTZ DEFAULT now()
);

-- subscriptions
CREATE TABLE subscriptions (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id) UNIQUE,
    stripe_customer_id VARCHAR(255) UNIQUE,
    stripe_subscription_id VARCHAR(255) UNIQUE,
    plan VARCHAR(50) NOT NULL,     -- free, creator, pro, agency
    status VARCHAR(50) NOT NULL,   -- active, trialing, past_due, cancelled
    current_period_end TIMESTAMPTZ,
    cancel_at_period_end BOOLEAN DEFAULT false,
    created_at TIMESTAMPTZ DEFAULT now(),
    updated_at TIMESTAMPTZ DEFAULT now()
);
```

---

## 11. Security Architecture

> **NON-NEGOTIABLE: Security is not a feature. It is a requirement. Every component defaults to maximum security.**

### Threat Model (STRIDE)

| Threat | Attack Vector | Mitigation |
|--------|--------------|-----------|
| Spoofing | Fake JWT tokens | RS256 key pairs, token rotation, short expiry (15m access / 7d refresh) |
| Tampering | Modified API requests | Request signing, input validation on ALL fields, Zod schemas |
| Repudiation | Denied API calls | Immutable audit logs in append-only table |
| Information Disclosure | SM token exposure | AES-256-GCM encryption, env-based master key, never log tokens |
| Denial of Service | API flooding | Rate limiting (per user + per IP), Cloudflare WAF |
| Elevation of Privilege | Stolen JWT | Short TTL, binding to device fingerprint, revocation list in Redis |

### Social Media Token Security (Critical)

Social OAuth tokens are the crown jewels. Compromise = account takeover.

**Encryption at rest:**
```go
// AES-256-GCM encryption for all OAuth tokens
// Master key derived from env var using PBKDF2 (100,000 iterations)
// Each token encrypted with unique nonce
// Stored as: nonce (12 bytes) || ciphertext || auth_tag (16 bytes)

type TokenVault struct {
    masterKey [32]byte  // derived from VAULT_MASTER_KEY env var
}

func (v *TokenVault) Encrypt(plaintext string) ([]byte, error) {
    // AES-256-GCM with random nonce
}

func (v *TokenVault) Decrypt(ciphertext []byte) (string, error) {
    // Authenticated decryption - fails if tampered
}
```

**Token lifecycle management:**
- Access tokens refreshed 5 minutes before expiry (proactive refresh)
- Refresh tokens rotated on every use (no static refresh tokens)
- All tokens revoked immediately on account disconnect
- Redis-based token revocation list for immediate logout
- Token binding: tokens bound to user_id + device_id (stolen token unusable on other device)

### API Security

```go
// All API endpoints enforce:
// 1. JWT validation (RS256)
// 2. Rate limiting (100 req/min per user, 20 req/min per endpoint per user)
// 3. Input validation (Zod-equivalent in Go using go-playground/validator)
// 4. SQL injection prevention (parameterized queries ONLY - no string interpolation)
// 5. CORS whitelist (only approved origins)
// 6. Security headers (CSP, HSTS, X-Frame-Options, X-Content-Type-Options)
// 7. Request size limits (10MB max body)
// 8. Content-type enforcement
```

### Authentication Security
- Passwords: Argon2id (memory: 64MB, iterations: 3, parallelism: 2)
- JWT: RS256 (RSA 4096-bit keypair), 15-minute access token TTL
- Refresh tokens: 64-byte crypto/rand hex, stored hashed (SHA3-256) in DB
- MFA: TOTP (RFC 6238) via Google Authenticator protocol
- Session revocation: Redis set of revoked JTIs (JWT IDs)
- Device fingerprint binding: user_agent + IP class bound to session

### Data Protection
- All PII encrypted at application layer before DB storage
- Database TLS connection mandatory (Neon enforces this)
- Cloudflare R2 server-side encryption for all stored media
- Zero plaintext secrets in codebase (all via environment variables)
- HashiCorp Vault integration for production secret rotation
- GDPR compliance: data deletion endpoint, data export endpoint
- Right to erasure: cascade deletes all user data including SM tokens

### Security Agent (Dedicated)
The SECURITY_AGENT runs continuously as a background process:
- Scans all new code for vulnerabilities before deployment
- Monitors for suspicious API patterns (brute force, credential stuffing)
- Alerts on anomalous SM token access patterns
- Rotates encryption keys on schedule
- Generates monthly security audit reports

---

## 12. Agent Configurations (WardPack v1)

All agent files are located in `.agent/agents/`. They must be uploaded to wardscribe.io.

### Agent Inventory

| Agent | File | Role | Confidence |
|-------|------|------|-----------|
| PRIME | PRIME_AGENT.md | Orchestrator | 0.98 |
| SOCIAL_ANALYTICS | SOCIAL_ANALYTICS_AGENT.md | SM data analysis | 0.95 |
| CONTENT_AI | CONTENT_AI_AGENT.md | Content generation | 0.94 |
| SCHEDULE_OPTIMIZER | SCHEDULE_OPTIMIZER_AGENT.md | Timing prediction | 0.96 |
| ML_PIPELINE | ML_PIPELINE_AGENT.md | Model training | 0.92 |
| SECURITY | SECURITY_AGENT.md | Security enforcement | 0.97 |
| MOBILE_BACKEND | MOBILE_BACKEND_AGENT.md | API + mobile layer | 0.93 |
| REVENUE | REVENUE_AGENT.md | Billing + monetization | 0.91 |
| GROWTH_MARKETING | GROWTH_MARKETING_AGENT.md | User acquisition | 0.89 |
| DATA_PIPELINE | DATA_PIPELINE_AGENT.md | Data ingestion | 0.94 |

See individual `.agent/agents/*.md` files for full WardPack v1 definitions.

### Orchestration Mode
- **Prime Agent** coordinates all specialists
- **Parallel execution** for independent tasks (analytics + scheduling can run concurrently)
- **Sequential** for dependent tasks (content generation depends on analytics)
- **Timeout:** 30 seconds per agent invocation
- **Retry policy:** 3 retries with exponential backoff

---

## 13. Skill Definitions (WardPack v1)

All skill files are located in `.agent/skills/`. They must be uploaded to wardscribe.io.

### Skill Inventory

| Skill | File | Input | Output |
|-------|------|-------|--------|
| social-profile-analyzer | social-profile-analyzer.yaml | account_data | profile_audit |
| content-performance-scorer | content-performance-scorer.yaml | post_history | performance_matrix |
| optimal-time-calculator | optimal-time-calculator.yaml | audience_data | time_slots |
| hashtag-recommender | hashtag-recommender.yaml | content + niche | hashtag_list |
| content-generator | content-generator.yaml | brief + profile | post_content |
| engagement-predictor | engagement-predictor.yaml | post_features | predicted_metrics |
| trend-detector | trend-detector.yaml | platform + niche | trending_topics |
| competitor-analyzer | competitor-analyzer.yaml | account_id | competitor_insights |
| monthly-content-planner | monthly-content-planner.yaml | profile + goals | 30_day_calendar |
| platform-adapter | platform-adapter.yaml | content + platforms | adapted_versions |

See individual `.agent/skills/*.yaml` files for full WardPack v1 definitions.

---

## 14. Revenue Model & Pricing

### Subscription Tiers

| Tier | Price/mo | Price/yr | Target | Features |
|------|---------|---------|--------|---------|
| **Free** | $0 | $0 | Discovery | 1 platform, 5 recommendations/mo, basic analytics |
| **Creator** | $29 | $290 (-17%) | Individual creators | 3 platforms, unlimited recommendations, monthly calendar, hashtag intelligence |
| **Pro** | $79 | $790 (-17%) | Power users / small biz | 5 platforms, all features, competitor analysis, custom brand voice, priority AI |
| **Agency** | $299 | $2,990 (-17%) | Agencies | 25 accounts, team seats (5), white-label reports, API access, dedicated support |
| **Enterprise** | Custom | Custom | Brands 1000+ followers | Unlimited, custom models, SLA, custom integrations |

### Unit Economics
- Gross margin target: 75-80% (AI inference costs are variable, managed tightly)
- Customer Acquisition Cost (CAC) target: < $30 for Creator, < $80 for Pro
- Lifetime Value (LTV) target: $350 Creator, $950 Pro, $3,600 Agency
- LTV/CAC ratio target: > 4x (healthy SaaS benchmark)

### Additional Revenue Streams
1. **Content Library Add-on** ($9/mo): Pre-written post templates by niche
2. **Competitor Intelligence Add-on** ($19/mo): Deep competitor monitoring
3. **AI Brand Voice Training** ($49 one-time): Train AI on brand's exact voice
4. **Managed Service** ($499/mo): Done-for-you social media management
5. **Affiliate Program** (30% for 12 months): Creator partners promoting SurePost

### Stripe Integration
- Stripe Checkout for subscriptions
- Stripe Billing Portal for self-service
- Stripe Connect for future marketplace features
- Usage-based billing for Agency tier (per-account pricing)

### Revenue Projections (Year 1)
| Month | Users | MRR | Notes |
|-------|-------|-----|-------|
| 1-3 | 0-500 | $0-$5K | Beta testing, free tier |
| 4-6 | 500-2000 | $5K-$30K | Product launch, early adopters |
| 7-9 | 2000-5000 | $30K-$80K | Growth phase, first marketing spend |
| 10-12 | 5000-12000 | $80K-$200K | Scale phase, virality kicking in |
| Month 12 ARR target | | $2.4M | |

---

## 15. Sales Strategy

### Sales Motion: Product-Led Growth (PLG)
Free tier is the acquisition engine. Users experience value before paying.

**Free tier hook:** "5 free recommendations per month - no credit card required"
**First conversion trigger:** When user receives first high-confidence recommendation and wants to act on more
**Second conversion trigger:** When user wants the monthly content calendar
**Enterprise conversion:** Inbound from agencies whose clients are already on Pro

### In-App Upgrade Triggers
1. After 5th recommendation used → "You've used all your recommendations. Upgrade to get unlimited."
2. When user tries to connect 4th platform → "Upgrade to Pro for 5 platforms"
3. When competitor analysis is previewed (blurred) → "Unlock full competitor insights with Pro"
4. When user publishes first AI-recommended post and sees engagement → "Your AI post got X% more engagement. See what Pro unlocks."

### Sales Channels
1. **Product-led self-serve** (primary, 70% of revenue) - Users convert themselves
2. **Content marketing** (secondary) - SEO articles rank for "best time to post on Instagram" etc.
3. **Influencer partnerships** - Micro-influencers (10K-100K followers) get free Pro, create content
4. **Agency partnerships** - Target marketing agencies with 5-20 client accounts
5. **Social media ads** (Meta + TikTok ads - ironic given the product) - Targeted at creators
6. **ProductHunt launch** - Target top 3 product of the day

### Pricing Psychology
- Annual plan framed as "get 2 months free" (vs "save 17%")
- Agency tier intentionally unpriced on landing page (forces conversation)
- Free tier has a "SurePost AI" watermark on exported calendars (virality)

---

## 16. Marketing & Advertising Plan

### Content Marketing (Organic, Long-term)
**SEO target keywords:**
- "best time to post on Instagram" (49,500 mo/searches)
- "best hashtags for Instagram 2026" (18,100 mo/searches)
- "how to grow on TikTok" (27,100 mo/searches)
- "social media content calendar template" (8,100 mo/searches)
- "AI social media tools" (6,600 mo/searches)

**Content strategy:**
- 2 SEO articles/week targeting high-intent keywords
- Free tools as lead magnets: "Best Time to Post on Instagram Calculator"
- Weekly newsletter: "Social Media Algorithm Updates" (builds audience)
- YouTube channel: "How We Grew [Account] 10K Followers in 30 Days Using AI"

### Paid Advertising

**Meta (Facebook + Instagram) Ads:**
- Target: creators, small business owners, marketing managers
- Format: Video testimonials showing engagement rate improvement
- Budget: $5K/mo (months 4-6), $15K/mo (months 7-12)
- CTA: "Start free - no credit card"

**TikTok Ads:**
- Target: Gen Z + Millennial creators
- Format: Native-feeling short videos showing "my posts before vs after SurePost"
- Budget: $3K/mo (months 5-12)

**Google Ads:**
- Target: "social media scheduler", "ai content tool", "how to get more followers"
- Format: Search ads + retargeting
- Budget: $2K/mo

### Influencer Marketing
**Tier 1 (micro-influencers, 10K-100K followers):**
- Give free Pro account
- Ask for honest review video
- Track performance with unique referral codes
- Budget: $0 (free product) + management time

**Tier 2 (mid-tier, 100K-500K followers):**
- Paid partnership ($500-$2K per post)
- Require verified metrics in the content (show their dashboard)
- Target niche: social media coaches, marketing educators

### Launch Week Strategy
1. **Day 1:** ProductHunt launch (coordinate upvotes from network)
2. **Day 2:** Twitter/X launch post with before/after metrics
3. **Day 3:** Reddit posts in r/socialmedia, r/Entrepreneur, r/Instagram
4. **Day 4:** Press outreach to TechCrunch, Social Media Examiner, Buffer Blog
5. **Day 5:** Email beta users asking for honest reviews on G2/Capterra
6. **Week 2:** First influencer posts go live

---

## 17. Go-to-Market Launch Strategy

### Phase 0: Private Beta (Month 1-2)
- 50-100 hand-picked beta users (mix of creators, small businesses)
- Free access to full Pro features
- Weekly feedback calls
- Rapid iteration based on feedback
- Goal: Product-market fit signal

### Phase 1: Public Beta (Month 3)
- Open beta with free tier + discounted paid tier (50% off)
- ProductHunt launch
- First influencer partnerships
- Goal: 500 active users, 50 paying

### Phase 2: General Availability (Month 4-6)
- Full pricing in effect
- Meta + TikTok ads live
- SEO content pipeline producing weekly
- Agency outreach program starts
- Goal: $30K MRR, 2,000 active users

### Phase 3: Growth (Month 7-12)
- Referral program (give 1 month free per referral that converts)
- Agency partner program (reseller discounts)
- Enterprise sales team (1 AE hired at $80K ARR milestone)
- International expansion (UK, Canada, Australia)
- Goal: $200K MRR, 15,000 active users

### App Store Optimization (ASO)
- App title: "SurePost - AI Social Media"
- Primary keyword: "social media AI"
- Screenshots: Before/after engagement rate screenshots
- Preview video: 30-second demo of AI recommendation in action
- Category: Business (primary), Social Networking (secondary)

---

## 18. Development Roadmap (Phased)

### Phase 1: Foundation (Weeks 1-6)
**Backend:**
- Go project scaffold with Gin, PostgreSQL, Redis
- User auth (register, login, JWT)
- Social account OAuth flow (Facebook/Instagram first)
- Token encryption vault
- Basic metrics sync job

**Mobile:**
- React Native + Expo scaffold
- Auth screens
- Connect accounts flow
- Basic dashboard shell

**AI:**
- Kimi AI client with function calling
- Profile audit prompt (first AI feature)
- Basic recommendation engine (rule-based first, then ML)

**Deliverable:** Users can register, connect Instagram, and receive a profile audit

### Phase 2: Core AI (Weeks 7-12)
**AI:**
- Best time predictor (training data collection + inference)
- Content generator with user voice matching
- Hashtag recommender
- First full recommendation with confidence score

**Mobile:**
- Recommendation detail screen
- Schedule a post (manual trigger, no auto-posting yet)
- Basic analytics screen

**Backend:**
- Scheduled post management
- Analytics ingestion pipeline
- Recommendation storage + retrieval

**Deliverable:** Users receive AI recommendations and can schedule posts

### Phase 3: Full Platform (Weeks 13-20)
**Platforms:**
- Add Twitter/X, TikTok, YouTube integrations
- Cross-platform content adapter
- Platform-specific optimization rules

**AI:**
- Monthly content calendar generation
- Competitor analysis
- Trend detection and integration
- Closed-loop feedback (track prediction accuracy)
- Confidence score v2 (multi-signal ensemble)

**Mobile:**
- Content calendar screen
- Competitor insights
- Full analytics dashboard
- Push notifications for optimal post times

**Deliverable:** Full 5-platform coverage, monthly calendar, 95% confidence scores live

### Phase 4: Revenue (Weeks 21-24)
- Stripe subscription integration
- Paywall enforcement in app
- Free tier limitations
- In-app upgrade flows
- Analytics for conversion funnel

**Deliverable:** Monetized product ready for launch

### Phase 5: Launch & Scale (Week 25+)
- Performance optimization (< 1.5s load times)
- App Store + Play Store submission
- ProductHunt launch
- First paid marketing campaigns
- Agency tier features
- Referral program

---

## 19. Infrastructure & DevOps

### Environments
| Environment | API | Database | Purpose |
|-------------|-----|----------|---------|
| development | localhost:8080 | Local PG | Local dev |
| staging | staging-api.surepost.app | Neon staging | Pre-release testing |
| production | api.surepost.app | Neon production | Live users |

### CI/CD Pipeline (GitHub Actions)
```yaml
# On PR:
# 1. Run tests (go test ./..., jest)
# 2. Run security scan (gosec, npm audit)
# 3. Run linter (golangci-lint, eslint)
# 4. Preview deployment (Vercel preview + Fly.io preview)

# On merge to main:
# 1. All PR checks
# 2. Build Docker image
# 3. Deploy to staging
# 4. Run integration tests against staging
# 5. Deploy to production (zero-downtime rolling deploy)
```

### Terraform Resources
- Neon PostgreSQL (production + staging branches)
- Upstash Redis (serverless)
- Cloudflare R2 bucket (media storage)
- Fly.io app (API server, 2 regions: US + EU)
- Vercel project (web dashboard)
- MeiliSearch Cloud
- Temporal Cloud

### Deployment Targets
- **API:** Fly.io (auto-scale 1-10 instances, US-east + EU-west)
- **Web:** Vercel (edge CDN, global)
- **Mobile:** Expo EAS (iOS App Store + Google Play Store)
- **Background Jobs:** Temporal Cloud (managed workflows)
- **Database:** Neon (serverless PG, auto-scale)
- **Cache:** Upstash Redis (serverless)

---

## 20. Monitoring & Observability

### Metrics Tracked
- API response time P50/P95/P99
- AI recommendation generation time
- Social API sync success rate
- Post publish success rate (per platform)
- Prediction accuracy (predicted vs actual engagement)
- User conversion funnel (free → paid)
- Churn rate

### Tooling
- **Sentry** - Error tracking + performance monitoring
- **OpenTelemetry** - Distributed tracing (API → AI → Social APIs)
- **ClickHouse** - Time-series analytics (post performance data)
- **Grafana** - Dashboard for all metrics
- **PagerDuty** - On-call alerts for P0/P1 incidents

### SLA Targets
| Metric | Target |
|--------|--------|
| API uptime | 99.9% |
| Recommendation generation | < 3 seconds |
| Post publishing | < 5 seconds from scheduled time |
| Data freshness | < 1 hour for metrics sync |

---

## 21. Risk Assessment & Mitigation

| Risk | Probability | Impact | Mitigation |
|------|------------|--------|-----------|
| Social API rate limits | High | High | Queue + retry system, per-user token pools |
| Social platform API deprecation | Medium | High | Adapter pattern - swap implementations without core changes |
| Kimi AI API downtime | Low | High | Fallback to cached recommendations + rule-based fallback |
| OAuth token expiry/revocation | High | Medium | Proactive refresh, graceful reconnect UX |
| User data breach | Low | Critical | AES-256-GCM, zero plaintext secrets, pen testing |
| Platform TOS violation | Medium | High | Legal review of each platform's developer TOS before launch |
| Competition from Buffer/Hootsuite | High | Medium | AI-first positioning, accuracy guarantee, speed advantage |
| Low prediction accuracy initially | Medium | High | Start conservative (serve only >90% confidence), improve with data |
| App Store rejection | Low | Medium | Follow Apple/Google developer guidelines strictly |

---

## 22. File Structure Reference

```
surepost/
├── PLAN.md                          # This file
├── .agent/
│   ├── AGENT.md                     # Prime orchestrator config
│   ├── agents/
│   │   ├── PRIME_AGENT.md
│   │   ├── SOCIAL_ANALYTICS_AGENT.md
│   │   ├── CONTENT_AI_AGENT.md
│   │   ├── SCHEDULE_OPTIMIZER_AGENT.md
│   │   ├── ML_PIPELINE_AGENT.md
│   │   ├── SECURITY_AGENT.md
│   │   ├── MOBILE_BACKEND_AGENT.md
│   │   ├── REVENUE_AGENT.md
│   │   ├── GROWTH_MARKETING_AGENT.md
│   │   └── DATA_PIPELINE_AGENT.md
│   ├── skills/
│   │   ├── social-profile-analyzer.yaml
│   │   ├── content-performance-scorer.yaml
│   │   ├── optimal-time-calculator.yaml
│   │   ├── hashtag-recommender.yaml
│   │   ├── content-generator.yaml
│   │   ├── engagement-predictor.yaml
│   │   ├── trend-detector.yaml
│   │   ├── competitor-analyzer.yaml
│   │   ├── monthly-content-planner.yaml
│   │   └── platform-adapter.yaml
│   └── rules/
│       ├── NO_EMOJI.md
│       └── SECURITY_ENFORCEMENT.md
├── surepost-api/                    # Go backend
├── surepost-mobile/                 # React Native + Expo
├── surepost-web/                    # Next.js 15 dashboard
├── infrastructure/                  # Terraform
└── docs/                            # Additional documentation
```

---

*Plan version 1.0 - SurePost AI Social Media Optimization Platform*
*Created: 2026-03-02 | Powered by Kimi AI + WardPack v1 Multi-Agent Architecture*
