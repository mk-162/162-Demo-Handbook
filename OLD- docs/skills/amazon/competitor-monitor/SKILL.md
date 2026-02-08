# Amazon Competitor Monitor

Systematic tracking of Amazon competitors: pricing changes, review patterns, new launches, and market positioning to inform strategic decisions.

## When to Use

- Weekly competitor check (recommended)
- Before pricing adjustments
- When planning new product launches
- After significant sales changes
- Quarterly strategic reviews

## Inputs Required

| Input | Source | Required |
|-------|--------|----------|
| Key product ASINs | GTSE catalog | ✅ |
| Competitor ASIN list | Research/Helium10 | ✅ |
| Category BSR baseline | Historical data | Recommended |
| Pricing thresholds | Finance/strategy | Recommended |

## Monitoring Workflow

### Step 1: Identify Top Competitors

**Per Key Product - Track Top 10:**

Selection Criteria:
1. Same primary keywords (search competitors)
2. Similar price point (±30%)
3. Appearing in "Customers also viewed"
4. Appearing in sponsored results for our keywords
5. Category bestseller rank leaders

**Key GTSE Competitors to Monitor:**
- RS Components (premium positioning)
- Generic Amazon sellers (price wars)
- Cableties.co.uk listings
- Amazon Basics (if in category)

**GTSE Competitor Tracking Template:**

```markdown
# Competitor Tracking: Heavy Duty Cable Ties 300mm

## GTSE Product
- ASIN: B0XXXXXXXXX
- Price: £X.XX
- BSR: #XXX in Cable Ties
- Rating: X.X ⭐ (X,XXX reviews)
- Key spec: 114kg (251lb) tensile strength

## Top 10 Competitors
| Rank | Brand | ASIN | Price | BSR | Rating | Reviews | Tensile |
|------|-------|------|-------|-----|--------|---------|---------|
| 1 | RS PRO | B0XXX | £X.XX | #XX | X.X | XXX | XX kg |
| 2 | Generic | B0XXX | £X.XX | #XX | X.X | XXX | XX kg |
| 3 | [Brand] | B0XXX | £X.XX | #XX | X.X | XXX | XX kg |
...

## Stainless Steel Cable Ties 300mm

## GTSE Product
- Key spec: 160kg (352lb) tensile strength, 316 marine grade

## Top Competitors
| Rank | Brand | ASIN | Price | Tensile | Grade |
|------|-------|------|-------|---------|-------|
| 1 | [Brand] | B0XXX | £X.XX | XX kg | 304/316 |
...
```

### Step 2: Track Pricing Changes

**Daily Price Monitoring:**

Set up alerts for:
- Price drops >10%
- Lightning deals activation
- Coupon additions
- Subscribe & Save changes
- Prime Day / Black Friday pricing

**Price Change Alert Thresholds:**

| Change Type | Threshold | Alert Priority |
|-------------|-----------|----------------|
| Competitor undercuts by >15% | Immediate | 🔴 High |
| Competitor undercuts by 5-15% | Within 24h | 🟡 Medium |
| Competitor raises price | Weekly digest | 🟢 Low |
| New coupon added | Within 24h | 🟡 Medium |

**Response Playbook:**

| Scenario | Our Response |
|----------|--------------|
| Major competitor drops 20%+ | Analyze: temporary or permanent? Check inventory levels |
| Competitor adds 15% coupon | Consider matching if margin allows |
| Multiple competitors drop | Market pressure - review our positioning |
| Competitor raises price | Opportunity to hold/raise ours |
| Lightning deal on competitor | Consider promotional response |

### Step 3: Monitor Reviews

**Weekly Review Analysis:**

Track for each competitor:
- New reviews in past 7 days
- Average rating trend
- Common complaints
- Common praise points

**Competitor Weakness Mining:**

Read 1-2 star reviews for:
- Product quality issues
- Sizing/specification problems
- Packaging complaints
- Delivery issues
- Customer service failures

**Opportunity Identification:**

```markdown
## Competitor Weakness Analysis: [Competitor Brand]

### Common Complaints (from 1-2 star reviews)
1. "Breaks too easily under load" - 47 mentions
2. "Not UV resistant, degrades outside" - 23 mentions
3. "Bag quantity wrong" - 15 mentions

### How GTSE is Better
1. Heavy Duty tensile: 114kg (251lb) - likely higher than competitor
2. Stainless Steel: 160kg (352lb) - marine grade 316
3. UV resistance: Rated -40°C to 85°C for outdoor
4. Quality control: UK-based, 3,000+ orders daily = systems in place

### Messaging Opportunities
- Add "114kg tensile strength" to title and bullets
- Highlight "-40°C to 85°C temperature range" for outdoor use
- Emphasize "UK quality checked" - family business accountability
- Show "25,000+ SKUs" scale = reliable supplier
```

### Step 4: Watch for New Launches

**Monitor For:**
- New ASINs from existing competitors
- New sellers entering the category
- Product variations (new sizes, colors, packs)
- Bundle offerings

**New Launch Alert Criteria:**

| Signal | Source | Action |
|--------|--------|--------|
| New ASIN in top 100 | Weekly BSR check | Analyze listing |
| New sponsored ad | Search monitoring | Review ad copy |
| "New Release" badge | Category browse | Full competitor analysis |
| Vine reviews appearing | Review monitoring | Product deep-dive |

### Step 5: Alert on Significant Changes

**Immediate Alerts (Slack/Email):**

| Event | Trigger | Response Time |
|-------|---------|---------------|
| 🔴 Major price drop | >20% reduction | Same day |
| 🔴 Stock-out | Competitor unavailable | Same day (opportunity) |
| 🟡 New launch | Top 50 BSR | Within 48 hours |
| 🟡 Review spike | +50 reviews in week | Within 48 hours |
| 🟢 Rating change | ±0.2 star shift | Weekly review |
| 🟢 BSR movement | ±50% rank change | Weekly review |

## Output: Weekly Competitor Digest

```markdown
# Weekly Competitor Digest

**Week of:** [Date Range]
**Category:** Cable Ties
**Prepared by:** [AI/Analyst]

## 📊 Market Overview

| Metric | This Week | Last Week | Trend |
|--------|-----------|-----------|-------|
| Our BSR | #XX | #XX | ↑/↓ |
| Our Price | £X.XX | £X.XX | → |
| Avg Competitor Price | £X.XX | £X.XX | ↓ |
| Our Review Count | X,XXX | X,XXX | +XX |

## 🔴 Urgent Alerts

### Competitor Price War
[Brand] dropped price from £X.XX to £X.XX (-XX%) on [date].
- **Impact:** Now cheapest in category
- **Recommendation:** [Hold/match/differentiate]

## 🟡 Notable Changes

### New Competitor Launch
[Brand] launched new [product] at £X.XX
- BSR after 1 week: #XXX
- Early reviews: X.X ⭐ (XX reviews)
- Threat level: Medium
- Key differentiator: [what they're claiming]

### Review Trend
[Brand] rating dropped from 4.5 to 4.2
- Primary complaint: [issue]
- Opportunity: Highlight our [counter-feature]

## 🟢 Opportunities Identified

1. **[Competitor] out of stock** (3 days now)
   - Consider: Bid up on their branded keywords
   
2. **[Competitor] negative reviews about [issue]**
   - Consider: Update our listing to highlight we don't have this issue

3. **Gap in market for [product type]**
   - Consider: Product development opportunity

## 📈 Pricing Recommendations

| Product | Current Price | Competitor Avg | Recommendation |
|---------|---------------|----------------|----------------|
| [ASIN] | £X.XX | £X.XX | Hold / Raise £0.XX / Match |

## 🎯 Action Items This Week

- [ ] [Specific action 1]
- [ ] [Specific action 2]
- [ ] [Specific action 3]

## Next Week Watch List
- [Brand] - potential price change incoming
- [New ASIN] - monitor early traction
```

## Competitor Intelligence Database

Maintain a living document:

```markdown
# Competitor Profiles

## [Competitor Brand 1]

### Overview
- **Amazon Storefront:** [link]
- **Estimated Monthly Revenue:** £XX,XXX
- **Focus Categories:** [list]
- **Brand Registry:** Yes/No

### Strengths
- [Strength 1]
- [Strength 2]

### Weaknesses
- [Weakness 1] - source: reviews
- [Weakness 2] - source: listing gaps

### Pricing Strategy
- [Premium/Value/Race-to-bottom]
- Typical discount patterns: [X% coupons on Y]

### Recent Activity
| Date | Action |
|------|--------|
| [Date] | [What they did] |
```

## Tools Used

- **Keepa**: Price and BSR tracking
- **Helium10 Market Tracker**: Competitor monitoring
- **DataDive**: Deep competitor analysis
- **Jungle Scout**: Category insights
- **Google Alerts**: Brand mention tracking

## Related Skills

- [Listing Audit](../listing-audit/SKILL) - Audit competitors' listings
- [PPC Optimizer](../ppc-optimizer/SKILL) - Competitive keyword bidding
- [Review Response](../review-response/SKILL) - Compare review strategies
