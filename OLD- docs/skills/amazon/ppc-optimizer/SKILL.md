# Amazon PPC Optimizer

Analyze and optimize Amazon Sponsored Products, Sponsored Brands, and Sponsored Display campaigns to reduce ACOS and maximize profitable sales.

## When to Use

- Weekly campaign optimization (recommended)
- When ACOS exceeds target threshold
- After launching new products
- Before/during peak seasons
- When scaling ad spend

## Inputs Required

| Input | Source | Required |
|-------|--------|----------|
| Campaign data export | Seller Central → Advertising Reports | ✅ |
| Target ACOS | Business decision | ✅ |
| Product margins | Sellerboard/internal data | ✅ |
| Search term report | Last 30-60 days | ✅ |
| Competitor ASINs | For product targeting | Optional |

## Optimization Workflow

### Step 1: Pull Campaign Data

Export from Seller Central → Advertising → Reports:
- **Sponsored Products Search Term Report** (60 days)
- **Sponsored Products Campaign Report** (60 days)
- **Targeting Report** (for product targeting campaigns)

Key metrics to extract:
```
Campaign Name | Ad Group | Targeting | Match Type | Impressions | 
Clicks | Spend | Sales | Orders | ACOS | CPC | CVR
```

### Step 2: Analyze ACOS by Campaign/Ad Group

**Categorize Campaigns:**

| ACOS Range | Category | Action |
|------------|----------|--------|
| 0-15% | 🟢 Winners | Scale budget +20-30% |
| 15-25% | 🟡 Performers | Maintain, optimize bids |
| 25-40% | 🟠 Break-even | Reduce bids, tighten targeting |
| 40%+ | 🔴 Losers | Pause or restructure |

**GTSE Benchmark Targets:**
| Product Category | Target ACOS | Break-even ACOS |
|------------------|-------------|-----------------|
| Cable Ties | 15% | 25% |
| Safety Equipment | 18% | 30% |
| Tools/Hardware | 20% | 35% |

### Step 3: Keyword Analysis

**Identify High-Spend Low-Convert Keywords:**

Filter search term report for:
```
Spend > £20 AND Orders = 0
OR
ACOS > 50% AND Spend > £10
```

**Action Matrix:**

| Clicks | Orders | ACOS | Action |
|--------|--------|------|--------|
| 20+ | 0 | ∞ | Add to negative (exact) |
| 10-19 | 0 | ∞ | Lower bid 30%, monitor |
| Any | 1+ | >50% | Lower bid to target ACOS |
| Any | 3+ | <20% | Increase bid, scale |

**GTSE Example - Cable Ties:**
```
❌ Negative: "free cable ties", "cable ties near me", "cheap cable ties wholesale"
✅ Scale: "heavy duty cable ties 300mm", "black nylon zip ties", "industrial cable ties uk"
```

### Step 4: Find Winning Keywords to Scale

**Criteria for Winners:**
- 3+ orders in 30 days
- ACOS below target
- High relevance to product

**Scaling Actions:**
1. Increase bid by 15-25%
2. Add as exact match in dedicated campaign
3. Create single-keyword ad group for top performers
4. Increase daily budget on winning campaigns

**Keyword Graduation Path:**
```
Auto Campaign → Broad → Phrase → Exact (dedicated)
```

### Step 5: Negative Keyword Strategy

**Types of Negatives:**

| Type | Use When | Example |
|------|----------|---------|
| Negative Exact | Specific term underperforms | "cable ties 100mm" (we don't sell) |
| Negative Phrase | Category irrelevant | "cable ties for hair" |

**Negative Keyword Sources:**
1. Search term report (high spend, no sales)
2. Competitor brand names (unless targeting)
3. Irrelevant use cases
4. Wrong sizes/colors we don't offer
5. B2C terms when targeting B2B

**GTSE Negative List Template:**
```
Campaign-Level Negatives:
- free, cheap, wholesale, bulk order, sample
- near me, amazon basics, [competitor brands]
- colors/sizes we don't stock

Product-Level Negatives:
- [specific wrong use cases]
- [wrong material searches]
```

### Step 6: Budget Reallocation

**Budget Optimization Formula:**

```
New Budget = Current Spend × (Target ACOS / Current ACOS)
```

**Reallocation Priority:**
1. Move budget FROM: Campaigns with ACOS > 40%
2. Move budget TO: Campaigns with ACOS < 20% that are budget-limited

**Signs Campaign Needs More Budget:**
- "Limited by budget" status
- Impression share below 10%
- Top of search impression share dropping
- High CVR but low impressions

## Output: Optimization Action Plan

```markdown
# PPC Optimization Report

**Date Range Analyzed:** [Date] to [Date]
**Total Spend:** £X,XXX
**Total Sales:** £X,XXX
**Overall ACOS:** XX%
**Target ACOS:** XX%

## Executive Summary
- X campaigns above target ACOS (action needed)
- X keywords identified for negative
- X keywords identified for scaling
- Estimated savings: £XXX/month

## Immediate Actions (This Week)

### 🔴 Pause/Reduce (High ACOS)
| Campaign | Current ACOS | Spend | Action |
|----------|--------------|-------|--------|
| [Name] | XX% | £XX | Reduce bid 30% |

### ➕ Add Negatives
| Keyword | Campaign | Spend | Orders | Action |
|---------|----------|-------|--------|--------|
| [term] | [camp] | £XX | 0 | Negative exact |

### 📈 Scale Winners
| Keyword | Campaign | ACOS | Orders | Action |
|---------|----------|------|--------|--------|
| [term] | [camp] | X% | XX | +25% bid, +budget |

## Budget Reallocation
| From Campaign | To Campaign | Amount |
|---------------|-------------|--------|
| [Low performer] | [High performer] | £XX/day |

## 30-Day Targets
- Reduce overall ACOS from XX% to XX%
- Increase profitable sales by XX%
- Reduce wasted spend by £XXX
```

## Campaign Structure Best Practices

### Recommended Structure for GTSE:

```
├── SP - [Product] - Auto
│   └── Single ad group, all match types
├── SP - [Product] - Research (Broad/Phrase)
│   └── Keyword harvesting from auto
├── SP - [Product] - Performance (Exact)
│   └── Graduated winners only
├── SP - [Product] - Product Targeting
│   └── Competitor ASINs
└── SB - [Category] - Brand Headline
    └── Brand awareness, category terms
```

### Bid Strategy by Campaign Type:

| Campaign Type | Bid Strategy | Adjustment |
|---------------|--------------|------------|
| Auto Discovery | Down only | -20% product pages |
| Research | Dynamic bids | +10% top of search |
| Performance | Fixed bids | +30% top of search |
| Brand Defense | Dynamic up/down | +50% top of search |

## Tools Used

- **Seller Central Advertising Console**: Campaign management
- **Helium10 Adtomic**: Automated optimization rules
- **DataDive**: Competitor bid analysis
- **Sellerboard**: True profit after ad spend

## Related Skills

- [Listing Audit](../listing-audit/SKILL) - Fix listings before scaling ads
- [Competitor Monitor](../competitor-monitor/SKILL) - Understand competitor ad strategy
- [Review Response](../review-response/SKILL) - Improve CVR through reviews
