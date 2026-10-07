# Klaviyo MCP Starter Kit — Manage Klaviyo Email & SMS with AI

> **This is a recipe repo.** The Synter MCP server itself lives at [Synter-Media-AI/mcp-server](https://github.com/Synter-Media-AI/mcp-server): create, launch, and optimize campaigns across the major ad platforms, with one-click install in Cursor, Claude, ChatGPT, and VS Code. Issues, releases, and ⭐ go there.


[![MCP Compatible](https://img.shields.io/badge/MCP-compatible-blue)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform: Klaviyo](https://img.shields.io/badge/Platform-Klaviyo-000000)](https://www.klaviyo.com)

**Bridge email marketing and paid advertising for maximum ROAS.** Open this repo in Amp, Cursor, or VS Code and manage Klaviyo lists, segments, and revenue data with AI — sync your top customers to ad platforms for lookalikes and suppress email subscribers from acquisition campaigns.

---

## Install

[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=synter-ads&config=eyJ1cmwiOiJodHRwczovL21jcC5zeW50ZXJhaS5jb20ifQ==)
[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_Synter-0098FF?logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=synter-ads&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.synterai.com%22%7D)

- **Cursor / VS Code:** click a button above, or open this repo — it ships `.cursor/mcp.json` and `.vscode/mcp.json`.
- **Claude Code:** this repo ships `.mcp.json`; or run:
  ```bash
  claude mcp add --transport http synter-ads https://mcp.synterai.com
  ```
- **Codex:**
  ```bash
  codex mcp add synter-ads --url https://mcp.synterai.com
  codex mcp login synter-ads
  ```
- **Claude Desktop:** copy `claude_desktop_config.json` into your Claude config directory (macOS: `~/Library/Application Support/Claude/`, Windows: `%APPDATA%\Claude\`) and replace the placeholder API key.

Your client opens Synter sign-in in the browser (OAuth). New here? Create an account at https://synterai.com/sign-up. Headless/CI fallback: send `X-Synter-Key` with a key from https://synterai.com/developer.

The MCP server itself: https://github.com/Synter-Media-AI/mcp-server

---

## Why Klaviyo + AI for Advertising?

Klaviyo is the email/SMS marketing platform of choice for 143,000+ ecommerce brands. It tracks every email open, click, purchase, and browse event — giving it the richest understanding of customer behavior in the ecommerce stack.

This data is transformative for advertising. Your Klaviyo segments reveal exactly who your best customers are: top 10% by revenue, repeat purchasers, VIP tier, recently churned. Each segment becomes a high-quality ad audience.

The smartest ecommerce brands use Klaviyo and ad platforms in a feedback loop: ads acquire new customers → Klaviyo nurtures them → purchase data feeds back into ad audiences → better targeting → lower CAC. An AI agent automates this entire loop.

**Best for:** Ecommerce and D2C brands, Shopify stores, any business using Klaviyo for email/SMS that also runs paid ads on Meta, Google, or TikTok.

---

## What You Can Do

| Capability | Example |
|-----------|---------|
| **Revenue Segments** | "Find my top 10% customers by lifetime revenue" |
| **Lookalike Seeds** | "Sync VIP customers to Meta for a 1% Lookalike audience" |
| **Customer Suppression** | "Exclude all Klaviyo subscribers from my Meta acquisition campaigns" |
| **Purchase Behavior** | "Which customers have purchased 3+ times in the last 90 days?" |
| **Churn Segments** | "Find customers who purchased 6+ months ago but not since" |
| **Flow Performance** | "How is my welcome series performing? Open rates, click rates, revenue?" |
| **Campaign Analytics** | "Which email campaign drove the most revenue this month?" |
| **Segment Building** | "Create a segment of customers who opened emails but haven't purchased" |
| **List Management** | "How many subscribers are on my main newsletter list?" |
| **Revenue Attribution** | "What percentage of revenue comes from email vs SMS vs ads?" |

---

## Example Conversations

### 1. Building the Ultimate Lookalike Audience

> **You:** I want to find more customers exactly like my best buyers. What data from Klaviyo should I use?
>
> **Agent:** Klaviyo has the richest customer data for building Lookalike audiences. Here's my tiered approach:
>
> **Tier 1 — Highest quality (your VIP seed):**
> - Segment: Top 10% by lifetime revenue + purchased 3+ times + last purchase within 90 days
> - Size: 1,240 customers
> - Upload to Meta → 1% Lookalike (~2.3M people)
> - These are your absolute best customers. The Lookalike will find people with similar purchase patterns.
>
> **Tier 2 — Repeat buyers (scale audience):**
> - Segment: Purchased 2+ times + average order value above $50
> - Size: 3,890 customers
> - Upload to Meta → 2% Lookalike (~4.6M people)
> - Slightly broader than Tier 1, good for scaling after Tier 1 is exhausted
>
> **Tier 3 — All buyers (maximum scale):**
> - Segment: At least 1 purchase
> - Size: 12,400 customers
> - Upload to Google Ads → Customer Match + Similar Audiences
> - Broadest audience, used when you need volume
>
> **Expected impact:** Tier 1 Lookalikes typically deliver 40-60% lower CPA than interest targeting. Your VIP customers have behavioral patterns (browsing, engagement, purchase frequency) that Meta's algorithm can match.
>
> **You:** Build all three tiers and sync to Meta.
>
> **Agent:** Done. Three Custom Audiences created on Meta with corresponding Lookalikes. I've also set up your 12,400 buyer list as an exclusion audience on your acquisition campaigns — no point paying to reach people Klaviyo already reaches for free.

### 2. Email Subscribers vs Paid Acquisition

> **You:** Am I wasting money showing ads to people who are already on my email list?
>
> **Agent:** Let me check the overlap between your Klaviyo subscribers and Meta ad audiences...
>
> **Overlap analysis:**
> - Klaviyo total subscribers: 48,200
> - Meta acquisition campaign reach (last 30 days): 890,000
> - **Estimated overlap: 6,200 people (0.7% of reach)**
>
> **The math on waste:**
> - Average CPM: $14.00
> - Impressions to overlapping subscribers: ~31,000
> - Wasted spend: ~$434/month
>
> **But here's the nuance:** Not all overlap is waste.
> - Subscribers who opened email in last 7 days → already engaged, don't need ads → SUPPRESS
> - Subscribers who haven't opened email in 90+ days → "email dead" → KEEP showing ads
> - Subscribers who abandoned cart → RETARGET (ads + email double-down works)
>
> **My recommendation:**
> 1. Suppress "active email subscribers" (opened email in last 30 days) from acquisition campaigns → saves $350/month
> 2. KEEP targeting "email dead" subscribers — ads are the only way to reach them now
> 3. Create a dedicated "cart abandoner" retargeting campaign that complements your Klaviyo abandonment flow

### 3. Revenue Attribution: Email vs Ads

> **You:** What percentage of our revenue comes from email vs ads?
>
> **Agent:** Pulling Klaviyo revenue attribution and comparing to your ad platform data...
>
> **Last 30 Days Revenue Attribution:**
>
> | Channel | Revenue | % of Total | Cost | ROAS |
> |---|---|---|---|---|
> | Klaviyo Email (Flows) | $48,200 | 32% | $450 (platform cost) | 107x |
> | Klaviyo Email (Campaigns) | $22,800 | 15% | $450 (platform cost) | 50x |
> | Klaviyo SMS | $8,400 | 6% | $1,200 (SMS cost) | 7x |
> | Meta Ads | $34,600 | 23% | $12,000 | 2.9x |
> | Google Ads | $24,200 | 16% | $8,500 | 2.8x |
> | Organic / Direct | $12,800 | 8% | $0 | ∞ |
>
> **Key insight:** Klaviyo drives 53% of revenue at a tiny fraction of the cost. But here's the catch — many of those email customers were *originally acquired* through ads. The real picture:
>
> **Customer journey:** Meta Ad → First Purchase → Klaviyo Welcome Flow → Second Purchase → Klaviyo Campaign → Third Purchase
>
> The ad platforms don't get credit for purchases 2 and 3, but they made them possible. Your true acquisition cost should factor in the lifetime value that email unlocks.
>
> **Recommendation:** Don't cut ad budget because "email drives more revenue." Instead, optimize ads for first-purchase acquisition and let Klaviyo handle retention. The combo is what drives your 53% email revenue.

### 4. Churn Recovery Campaign

> **You:** I want to win back customers who stopped buying.
>
> **Agent:** Let me identify churned customers in Klaviyo...
>
> **Churn segments:**
>
> | Segment | Criteria | Count | Avg Previous LTV |
> |---|---|---|---|
> | Recently Lapsed | Purchased 3-6 months ago, not since | 2,840 | $120 |
> | Lapsed | Purchased 6-12 months ago, not since | 1,920 | $95 |
> | Deeply Lapsed | Purchased 12+ months ago, not since | 3,100 | $72 |
>
> **Multi-channel win-back strategy:**
>
> **Email (Klaviyo flow — you should already have this):**
> - 3-email sequence: "We miss you" → "Here's what's new" → "10% off, last chance"
>
> **Ads (complement the email flow):**
> - **Recently Lapsed (2,840):** Highest recovery potential. Upload to Meta → show new product launches and bestsellers. Budget: $15/day.
> - **Lapsed (1,920):** Medium potential. Upload to Meta → show "We miss you — 15% off" offer with new products they haven't seen. Budget: $10/day.
> - **Deeply Lapsed (3,100):** Low potential but large audience. Upload to Google Display → low-cost brand awareness. Budget: $5/day.
>
> **Why ads + email is better than email alone:** Your email open rate for lapsed customers is probably 10-15%. Ads reach the other 85-90% who won't open your email. The double-exposure increases win-back rates by 30-40%.

### 5. SMS + Paid Ads Coordination

> **You:** I just launched SMS marketing on Klaviyo. How should it work with my ads?
>
> **Agent:** SMS and ads should complement each other, not compete. Here's the coordination framework:
>
> **Rule 1: Never run the same offer on SMS and ads simultaneously to the same audience.**
> - If you SMS "Flash Sale: 20% off today only" to your full list, suppress that list from ad platforms for 24 hours. Otherwise you're paying to tell people something they already know.
>
> **Rule 2: Use SMS for urgency, ads for awareness.**
> - SMS: "Your cart is expiring in 1 hour — complete your purchase"
> - Ads: "New arrivals you'll love" (discovery and browsing)
>
> **Rule 3: SMS subscribers make the best ad audiences.**
> - People who opted into SMS are your most engaged customers
> - Upload SMS subscribers to Meta → 1% Lookalike → find more high-engagement customers
> - SMS subscribers who also purchase → best seed audience you'll ever have
>
> **Coordination calendar:**
> | Day | SMS | Ads |
> |---|---|---|
> | Monday | — | Product discovery ads |
> | Tuesday | — | Product discovery ads |
> | Wednesday | New Arrival Alert | Suppress SMS list from ads |
> | Thursday | — | Retarget non-openers with same products |
> | Friday | Flash Sale 🎉 | Suppress SMS list from ads |
> | Weekend | — | Retarget with sale items |

---

## Klaviyo Tips for Ad Targeting

1. **Top 10% by revenue = best Lookalike seed.** This segment outperforms "all customers" as a Lookalike seed by 40-60% on CPA. Quality > quantity for seed audiences.
2. **Suppress active email subscribers from acquisition.** If someone opens your emails regularly, don't waste ad budget reaching them. They're already engaged.
3. **"Email dead" subscribers need ads.** Subscribers who haven't opened in 90+ days won't see your emails. Ads are the only channel that can re-engage them.
4. **Cart abandoner double-down.** Run Klaviyo's abandonment flow AND retargeting ads simultaneously. The multi-channel approach recovers 30-40% more carts than email alone.
5. **Revenue attribution is misleading.** Email "drives" revenue, but ads acquired the customer. Track first-purchase source separately from repeat-purchase source.
6. **Refresh audiences monthly.** Customer purchase behavior changes. Last month's VIPs might be this month's churners.
7. **SMS subscribers = highest-intent Lookalike seed.** People who give you their phone number are deeply engaged. Use this segment as your premium Lookalike source.

---

## FAQ

### Is there an MCP for Klaviyo?
Yes — this repo. It pre-configures the Synter MCP server for Klaviyo management. Works with Amp, Cursor, VS Code, and Claude Desktop.

### Can I sync Klaviyo segments to Meta for Lookalikes?
Yes. The agent exports Klaviyo segment data, hashes emails, and uploads as Meta Custom Audiences for Lookalike creation.

### Does this replace Klaviyo's built-in Meta integration?
It complements it. Klaviyo's native Meta integration syncs lists, but the AI agent adds intelligence — choosing the right segments, building suppression logic, and coordinating timing.

### Can the agent create Klaviyo flows?
The agent focuses on reading segments, lists, and performance data for ad targeting. Flow creation is best done in Klaviyo's visual builder.

### How does this help lower my CAC?
By using Klaviyo's rich purchase data to build better ad audiences (Lookalikes from VIPs), suppress waste (don't advertise to active subscribers), and coordinate channels (email + ads together).

---

## Related Repos

- [shopify-agent](https://github.com/Synter-Media-AI/shopify-agent) — Shopify product & customer data
- [meta-ads-agent](https://github.com/Synter-Media-AI/meta-ads-agent) — Meta Custom Audiences & Lookalikes
- [google-ads-agent](https://github.com/Synter-Media-AI/google-ads-agent) — Google Customer Match
- [audience-sync-agent](https://github.com/Synter-Media-AI/audience-sync-agent) — Multi-platform audience sync
- [cross-platform-ads-agent](https://github.com/Synter-Media-AI/cross-platform-ads-agent) — Multi-channel reporting
- [tiktok-ads-agent](https://github.com/Synter-Media-AI/tiktok-ads-agent) — TikTok Custom Audiences

---

## License

MIT — see [LICENSE](LICENSE) for details.

Built by [Synter](https://synterai.com) · [Get API Key](https://synterai.com/developer) · [Documentation](https://synterai.com/docs)
