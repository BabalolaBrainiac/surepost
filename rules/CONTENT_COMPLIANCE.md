# CONTENT_COMPLIANCE

version: 2.0.0
scope: all agents, all platforms
enforcement: mandatory — quality gate agent will reject any post that violates these rules

---

## 1. FTC Disclosure Requirements

All posts that include affiliate links, sponsored content, or paid partnerships must include a clear and conspicuous disclosure. This is a legal requirement in the United States and most major markets.

### Required Disclosure Formats by Platform

**Instagram**
- Reel/Post/Carousel: `#ad` or `#sponsored` at the start of the caption (not buried after more lines)
- Story: Text overlay on the frame reading "Paid partnership" or "#ad"
- All disclosures must appear before the "more" cutoff in captions

**TikTok**
- Video description: `#ad` within the first line of the description
- On-screen overlay text in the first 3 seconds if verbally mentioned
- Do not use abbreviations like "sp" or "collab" — use `#ad` or `#sponsored`

**Twitter/X**
- Include `[ad]` or `#ad` in the tweet text itself, not in a reply
- For threads: disclose on every tweet in the thread that references the product

### Approved Disclosure Language

```
#ad — i earn a commission if you sign up
#ad — affiliate link, i may earn a commission
Sponsored. I partnered with [brand] on this.
[ad] affiliate link below
```

### Prohibited Disclosure Patterns

- Burying `#ad` after 20+ hashtags
- Using `#sp`, `#collab`, `#gifted` without also including `#ad` or `#sponsored`
- Mentioning "link in bio" without disclosing the affiliate nature
- Adding disclosures only in comments, not the post itself

---

## 2. Platform Terms of Service Compliance

### Instagram (Meta)
- No artificial engagement (do not buy likes, followers, or comments)
- No spam posting — maximum 3 posts per day on main feed
- No misleading claims about income ("guaranteed income", "make $10K overnight")
- Reels must be original content — no reuploading TikTok watermarked content
- Stories can link to affiliate products only if account has 10K+ followers or verified

### TikTok
- All affiliate links must go through TikTok's link-in-bio or TikTok Shop — no direct competitor platform links in captions
- No income guarantees or get-rich-quick framing
- No copyrighted music unless cleared via TikTok Commercial Music Library
- Videos must be original — no screen recordings of other creators without commentary

### Twitter/X
- No coordinated inauthentic behavior
- No misleading affiliate disclosures
- Threads must be genuine threads — do not pad with filler tweets to artificially boost impression count
- Premium revenue share requires account to be Premium subscriber and meet eligibility thresholds

---

## 3. Financial Content Rules

Financial content is subject to additional scrutiny. The following rules apply to all posts touching money, investing, or income.

### Always Include (when relevant)
- "This is not financial advice" when discussing specific investment strategies, trading, or crypto
- Clear context that results shown are not typical ("results may vary", "my personal experience")
- Distinction between affiliate commission income and platform monetization income

### Never Include
- Guaranteed return claims ("this will make you $X")
- Specific investment recommendations without disclaimer ("buy this stock/coin now")
- Fabricated income screenshots or edited earnings dashboards
- Claims of special insider knowledge about market movements

### Income Claims — Approved Framing
```
✓ "i made $X last month using this tool — here's exactly how"
✓ "this approach can generate income — my experience:"
✓ "the potential is $X — results depend on effort and audience"

✗ "you will make $X using this"
✗ "guaranteed passive income"
✗ "this made me rich and it will make you rich too"
```

---

## 4. Content Authenticity Standards

### Prohibited Content Patterns
The quality gate agent will auto-reject posts containing any of the following:

- AI-sounding openers: "in this post i will", "hello everyone", "today we are going to", "as an ai"
- Excessive hedge language: "it's important to note that", "please keep in mind that"
- Corporate speak: "leverage synergies", "actionable insights", "game-changer" without specifics
- Vague value claims: "this will change your life" without specific mechanism
- Fake urgency: "limited time only" or "only X spots left" when no actual scarcity exists

### Voice Requirements
All content must sound like a real person who knows their subject deeply:
- Short, direct sentences
- First-person perspective on tips and results
- Specific numbers over vague claims ("3.2x reach" not "way more reach")
- Conversational — as if texting a smart friend, not writing a press release

---

## 5. Competitor Mention Policy

- Never mention competitor accounts by name in a negative context
- Do not replicate competitor hooks verbatim — paraphrase and improve
- Competitor analysis is for intelligence only — posts must be original
- Do not claim to have "exclusive" information that is publicly available

---

## 6. Crisis and Sensitivity Protocol

If trending news involves tragedy, violence, natural disasters, or geopolitical conflict:
- Pause all promotional or affiliate content for that platform for 24 hours
- If a post is already scheduled, delay it — do not post commercial content during breaking crisis news
- Educational or genuinely supportive content may still post at quality gate discretion

---

## 7. Quality Gate Integration

The QUALITY_GATE_AGENT enforces these rules as the final check before any post is scheduled. A post fails quality gate if:

| Rule Category | Threshold |
|---|---|
| Missing FTC disclosure on affiliate post | AUTO FAIL |
| Income claim without disclaimer | AUTO FAIL |
| Prohibited opener detected | AUTO FAIL |
| Platform TOS violation detected | AUTO FAIL |
| Fake scarcity / misleading urgency | AUTO FAIL |
| Disclosure buried after 10+ lines | AUTO FAIL |

Posts that fail are regenerated up to 3 times. After 3 failures, the post is flagged for human review and removed from the daily schedule.
