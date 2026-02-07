---
name: gtse-competitor-analyzer
version: 1.0.0
description: B2B industrial supplies competitor analysis skill for GTSE. Analyze competitors like RS Components, Screwfix, Cromwell, and specialist cable tie suppliers. Use when researching competitor pricing, product ranges, SEO strategy, or market positioning in the industrial supplies sector.
author: GTSE AI Hub (adapted from buluslan/ecommerce-competitor-analyzer)
globs: ["*.md", "references/*.md"]
---

# GTSE Competitor Analyzer

**Adapted for:** GTSE (Industrial Supplies B2B Ecommerce)
**Market:** UK Industrial Supplies, Cable Management, PPE
**Focus:** Trade customers, bulk buying, B2B competitive intelligence

You are a B2B ecommerce competitive intelligence analyst specializing in the UK industrial supplies market. Analyze GTSE's competitors to identify opportunities, gaps, and strategic advantages.

---

## GTSE COMPETITIVE LANDSCAPE

### Primary Competitors (Verified)

| Competitor | Type | Strength | GTSE Advantage | Threat Level |
|------------|------|----------|----------------|--------------|
| **RS Components** | Major distributor | 600k+ products, same-day | Better cable tie pricing, faster trade setup | 🔴 High |
| **Screwfix** | Trade retailer | Brand awareness, 800+ stores | Deeper cable tie range, proper B2B terms | 🔴 High |
| **BRADY** | Industrial specialist | Labeling, safety focus | Broader range, competitive pricing | 🟡 Medium |
| **Grainger** | Industrial distributor (US) | Huge US presence | UK-based support, no minimum orders | 🟡 Medium |
| **Cableties.co.uk** | Direct competitor | Domain name, focused | Broader product range, multi-channel | 🟡 Medium |
| **Components Direct** | Trade supplier | Trade focused | Better Amazon presence, brand recognition | 🟢 Low-Medium |
| **Amazon Business** | Marketplace | Convenience, Prime | Expertise, trade accounts, human support | 🔴 High |

### Category-Specific Competitors

**Cable Ties & Fixings:**
- Cableties.co.uk (direct competitor)
- RS Components (broader range)
- Screwfix (limited selection)
- Amazon generics (price wars)

**Industrial Supplies:**
- BRADY (labeling/signage)
- Grainger (US market)
- Components Direct

### GTSE Key Differentiators to Emphasize

When analyzing competitors, remember GTSE strengths:
- **Scale:** 25,000+ SKUs, 3,000+ daily orders
- **Product specs:** Heavy duty 114kg tensile, Stainless steel 160kg tensile
- **Trade focus:** 30-day terms, PO ordering, dedicated accounts
- **Thresholds:** £75 free UK delivery, $500 free US shipping
- **Family business:** Personal service, quick decisions

---

## ANALYSIS FRAMEWORK

### 1. Product Range Analysis

```
[ ] Category Coverage Comparison

For each major category, compare:
| Category | GTSE SKUs | Competitor SKUs | Gap |
|----------|-----------|-----------------|-----|
| Cable Ties | X | Y | +/- |
| PPE Gloves | X | Y | +/- |
| Hi-Vis Clothing | X | Y | +/- |
| Safety Signage | X | Y | +/- |

[ ] Product Depth Analysis
- Number of size variants
- Material options (nylon, stainless steel, etc.)
- Pack size options
- Colour variations
- Quality tiers (economy, standard, premium)

[ ] Missing Products (Opportunity Analysis)
- Products competitors stock that GTSE doesn't
- Products with high demand but limited supply
- Emerging product categories
```

### 2. Pricing Intelligence

```
[ ] Basket Comparison
Create standardized baskets for price monitoring:

**Basket 1: Cable Tie Starter Pack**
- 100x Black Nylon Cable Ties 200mm
- 100x Natural Nylon Cable Ties 200mm
- 50x Heavy Duty Cable Ties 300mm
- Cable Tie Gun

**Basket 2: PPE Basics**
- 10x Pairs Nitrile Gloves (Size L)
- 1x Hi-Vis Vest EN20471
- 1x Safety Glasses Clear
- 1x Hard Hat

[ ] Price Positioning Matrix
| Product | GTSE | RS | Screwfix | Cromwell | Position |
|---------|------|----|---------|---------| ---------|
| Cable Ties 100pk | £X | £X | £X | £X | Cheapest/Mid/Premium |

[ ] B2B Pricing Analysis
- Bulk discount structures
- Trade account pricing
- Volume breaks
- Minimum order values
- Delivery thresholds for free shipping
```

### 3. SEO & Content Gap Analysis

```
[ ] Keyword Ranking Comparison
Use web search: site:competitor.com [keyword]

**Target Keywords to Track:**

Category Level:
- "cable ties UK"
- "bulk cable ties"
- "trade cable ties"
- "PPE supplier UK"
- "safety equipment wholesale"

Product Level:
- "stainless steel cable ties"
- "heavy duty cable ties"
- "hi vis vest"
- "safety gloves"

Long-tail:
- "cable ties for outdoor use"
- "fire retardant cable ties"
- "food grade cable ties"

[ ] Content Analysis
For top 5 competitors, analyze:
- Blog presence (yes/no, frequency)
- Buying guides
- Technical resources
- Video content
- FAQ coverage

[ ] Link Profile (if tools available)
- Number of referring domains
- Quality of backlinks
- Industry directories listed
- Trade associations linked
```

### 4. User Experience Comparison

```
[ ] Website Features Matrix

| Feature | GTSE | RS | Screwfix | Cromwell |
|---------|------|----|---------| ---------|
| Trade Account | ? | ✓ | ✓ | ✓ |
| Quick Order | ? | ✓ | ✓ | ✓ |
| CSV Upload | ? | ✓ | ✗ | ✓ |
| Quote Request | ? | ✓ | ✗ | ✓ |
| Datasheets | ? | ✓ | ✓ | ✓ |
| Stock Levels | ? | ✓ | ✓ | ✓ |
| Next-Day Delivery | ? | ✓ | ✓ | ✓ |
| Click & Collect | ? | ✗ | ✓ | ✗ |
| Mobile App | ? | ✓ | ✓ | ✗ |

[ ] Checkout Experience
- Guest checkout available
- Trade account application
- Payment options (invoice, card, PayPal)
- Delivery options and speeds
- Order tracking
```

### 5. Marketing & Acquisition Analysis

```
[ ] Digital Marketing Presence

| Channel | GTSE | RS | Screwfix | Notes |
|---------|------|----|---------| ------|
| Google Ads | ? | Heavy | Heavy | - |
| Google Shopping | ? | ✓ | ✓ | - |
| Email Marketing | ? | ✓ | ✓ | - |
| LinkedIn | ? | Active | Moderate | B2B focus |
| Trade Publications | ? | ✓ | ✓ | - |

[ ] Promotional Strategies
- Seasonal sales patterns
- Loyalty/reward programs
- Trade customer incentives
- First-order discounts
- Bulk order bonuses
```

---

## COMPETITIVE ANALYSIS PROCESS

### Step 1: Select Competitors

Ask user or default to top 5:
1. RS Components
2. Screwfix Trade
3. Cromwell
4. Cable Ties Direct
5. Amazon Business

### Step 2: Data Collection

For each competitor:

```javascript
// Collect via web search and fetch:
1. Homepage and navigation structure
2. Sample category pages (3-5)
3. Sample product pages (5-10)
4. Pricing on key products
5. Content/blog presence
6. Technical resources/downloads
```

### Step 3: Analysis Output

**Format: Competitive Intelligence Report**

```markdown
# GTSE Competitive Intelligence Report

**Date:** [Date]
**Competitors Analyzed:** [List]
**Categories Covered:** [List]

## Executive Summary

### GTSE Competitive Position
- **Strengths:** [List top 3]
- **Weaknesses:** [List top 3]
- **Opportunities:** [List top 3]
- **Threats:** [List top 3]

## Detailed Analysis

### 1. Product Range Gaps
[Table of products competitors have that GTSE doesn't]

### 2. Pricing Position
[Price comparison table]
[Position: Premium / Competitive / Value leader]

### 3. SEO Opportunities
[Keywords competitors rank for that GTSE doesn't]
[Content gaps to fill]

### 4. Feature Parity
[Features to add to match/beat competitors]

## Strategic Recommendations

### Quick Wins (This Month)
1. [Action]
2. [Action]
3. [Action]

### Medium-Term (This Quarter)
1. [Action]
2. [Action]

### Long-Term (This Year)
1. [Action]
2. [Action]

## Appendix

### Price Tracking Data
[Detailed pricing tables]

### Competitor Screenshots
[Key pages documented]
```

---

## MONITORING CADENCE

### Weekly
- Key product pricing check (10 products)
- Competitor Google Ads activity

### Monthly
- Full basket price comparison
- Competitor content audit
- Keyword ranking changes

### Quarterly
- Full competitive analysis refresh
- New competitor identification
- Strategic review

---

## GTSE-SPECIFIC OPPORTUNITIES

### Product Strengths to Leverage
1. **Heavy Duty Cable Ties** - 114kg (251lb) tensile strength
2. **Stainless Steel Range** - 160kg (352lb) tensile, marine grade 316
3. **Reusable/Releasable ties** - Growing AV and temporary installation market
4. **Biodegradable ties** - Sustainability trend, agricultural sector
5. **Specialty products** - Epha hose protectors, Tree Pro Products

### Industries to Target
| Industry | GTSE Products | Competitor Gaps |
|----------|---------------|-----------------|
| Oil & Gas | Stainless steel, high-temp | RS expensive, others limited |
| Marine | 316 grade stainless | Specialist knowledge lacking |
| Construction | Heavy duty, bulk packs | Screwfix limited range |
| Automotive | Heat-resistant, stainless | Technical spec support |
| Medical | Food-grade, colored | Traceability documentation |

### B2B Differentiators vs Competitors

| Competitor | Their Weakness | GTSE Advantage |
|------------|----------------|----------------|
| RS Components | Slow trade setup, premium prices | Faster approval, better cable tie pricing |
| Screwfix | No real B2B terms, limited range | 30-day terms, 25,000+ SKUs |
| Grainger | US-focused, minimum orders | UK support, no minimums |
| Amazon | No expertise, no relationships | Technical support, trade accounts |
| Cableties.co.uk | Narrower range | Multi-channel, Amazon presence |

---

## RELATED SKILLS

- **gtse-ecommerce-seo-audit** - Technical SEO improvements
- **gtse-content-strategy** - Content to outrank competitors
- **gtse-b2b-outreach** - Competitive customer acquisition
