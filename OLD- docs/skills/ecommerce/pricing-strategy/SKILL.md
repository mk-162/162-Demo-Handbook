---
name: pricing-strategy
title: Ecommerce Pricing Strategy & Optimization
description: Comprehensive pricing framework covering competitor monitoring, margin analysis, promotional planning, bundling, B2B tiers, and marketplace rules
version: 1.0.0
tags: [pricing, ecommerce, margins, promotions, b2b, amazon]
---

# Ecommerce Pricing Strategy & Optimization

## Purpose

This skill provides a complete framework for pricing decisions across ecommerce channels. It covers the strategic, tactical, and operational aspects of pricing including competitor analysis, margin optimization, promotional calendars, bundle strategies, B2B tier structures, and Amazon-specific pricing rules.

**Use this skill when:**
- Setting prices for new products
- Reviewing pricing for existing products
- Planning promotional campaigns
- Optimizing margins across product lines
- Setting up B2B customer tiers
- Managing Amazon pricing and compliance
- Responding to competitor price changes

**GTSE Context:** For trade and industrial supply distributors, pricing must balance competitiveness (against Toolstation, Screwfix, Amazon) with sustainable margins, while serving both B2C customers and B2B trade accounts with different pricing expectations.

## Inputs

- `product_sku`: Product identifier
- `cost_price`: Landed cost including shipping, duties, packaging
- `competitor_prices`: Array of competitor prices for same/similar products
- `target_margin`: Desired gross margin percentage
- `channel`: Sales channel (website, Amazon, eBay, trade counter)
- `customer_segment`: Customer type (B2C, trade bronze, trade silver, trade gold)
- `product_category`: Category for category-level strategies

## Prerequisites

Before implementing pricing strategies:

1. **Cost Data**
   - Accurate landed costs for all products
   - Understanding of variable costs (payment processing, shipping)
   - Fixed cost allocation methodology

2. **Competitor Intelligence**
   - List of key competitors to monitor
   - Competitor price tracking tools
   - Category benchmark data

3. **Sales Data**
   - Historical sales by price point
   - Price elasticity indicators
   - Customer segment analysis

4. **Channel Understanding**
   - Fee structures for all channels
   - Pricing rule requirements (Amazon MFN/FBA parity)
   - Channel-specific customer expectations

---

## Procedure

### Step 1: Competitor Price Monitoring

**What:** Establish systematic tracking of competitor prices to inform pricing decisions.

**How:**

#### 1.1 Identify Competitors to Monitor

```markdown
## Competitor Monitoring Matrix

### Tier 1: Direct Competitors (Same products)
| Competitor | Type | Monitor Frequency |
|------------|------|-------------------|
| Toolstation | Trade retailer | Daily |
| Screwfix | Trade retailer | Daily |
| Amazon (marketplace) | Marketplace | Daily |
| eBay (category) | Marketplace | Weekly |

### Tier 2: Category Competitors (Same category)
| Competitor | Type | Monitor Frequency |
|------------|------|-------------------|
| RS Components | B2B specialist | Weekly |
| Cromwell | Industrial supplier | Weekly |
| Zoro | Online trade | Weekly |

### Tier 3: Indirect Competitors (Occasional overlap)
| Competitor | Type | Monitor Frequency |
|------------|------|-------------------|
| B&Q | DIY retail | Monthly |
| Wickes | DIY retail | Monthly |
| Local trade counters | Traditional | Monthly |
```

#### 1.2 Set Up Monitoring System

**Manual Monitoring (Small catalog):**
```markdown
## Daily Price Check Spreadsheet

| Product | Our Price | Toolstation | Screwfix | Amazon | Status |
|---------|-----------|-------------|----------|--------|--------|
| Cable Ties 300mm 100pk | £8.99 | £9.49 | £9.29 | £8.75 | ✅ Competitive |
| Wood Screws 4x40 200pk | £12.99 | £11.99 | £12.49 | £13.25 | ⚠️ Review |
| Safety Glasses 6pk | £15.99 | £14.99 | £15.99 | £12.99 | ⚠️ Review |
```

**Automated Monitoring (Recommended for 100+ SKUs):**

Tools to consider:
- **Prisync** - Competitor price tracking
- **Competera** - Dynamic pricing platform
- **RepricerExpress** - Amazon repricing
- **Price2Spy** - Multi-competitor monitoring
- **Import.io** - Custom scraping

**Alert Configuration:**
```markdown
### Price Alert Rules

**Critical Alert (Immediate review):**
- Any competitor drops price >15% on tracked product
- Amazon loses Buy Box to lower-priced seller
- Key competitor runs flash sale on our category

**Standard Alert (Weekly review):**
- Competitor price changes >5% on tracked products
- New competitor enters monitored category
- Competitor launches bundle or multi-buy

**Informational (Monthly review):**
- Overall market price trends
- Competitor out-of-stock notices
- New product launches by competitors
```

#### 1.3 Competitive Position Analysis

For each product category, define target position:

```markdown
## Category Positioning Strategy

### Cable Ties
**Position:** Price leader (lowest or 2nd lowest)
**Rationale:** High volume, commodity product, price sensitive buyers
**Target:** Within 5% of lowest competitor

### Hand Tools
**Position:** Value leader (mid-market with quality story)
**Rationale:** Quality matters, not pure commodity
**Target:** Within 10% of mid-market, emphasize quality/warranty

### Safety Equipment
**Position:** Premium option (quality and compliance focus)
**Rationale:** Buyers want assurance, not cheapest
**Target:** Can be 10-15% above market with certifications

### Speciality Products
**Position:** Competitive (match market)
**Rationale:** Low volume, niche, less price sensitive
**Target:** Within 5% of market average
```

**Tools:** Price monitoring software, spreadsheets, alerts

**Output:** Competitor price database with monitoring alerts configured

---

### Step 2: Margin Analysis Framework

**What:** Calculate true profitability to inform pricing decisions.

**How:**

#### 2.1 Understanding True Costs

```markdown
## Product Cost Breakdown Template

### Product: Cable Ties 300mm Black 100pk
**SKU:** CT300BK100

### Direct Costs
| Cost Component | Amount | % of Sell Price |
|----------------|--------|-----------------|
| Purchase cost (ex works) | £2.00 | 22.2% |
| Freight/shipping | £0.30 | 3.3% |
| Duty/customs | £0.00 | 0% |
| Packaging | £0.15 | 1.7% |
| **Total Landed Cost** | **£2.45** | **27.2%** |

### Variable Costs (per transaction)
| Cost Component | Amount | % of Sell Price |
|----------------|--------|-----------------|
| Payment processing (2.5%) | £0.22 | 2.5% |
| Picking/packing | £0.50 | 5.6% |
| Shipping label | £2.80 | 31.1% |
| Returns allowance (3%) | £0.27 | 3.0% |
| **Total Variable** | **£3.79** | **42.1%** |

### Channel Costs (varies by channel)
| Channel | Fee | % of Sell Price |
|---------|-----|-----------------|
| Website | £0.00 | 0% |
| Amazon FBA | £4.64 | 51.6% |
| eBay | £1.26 | 14.0% |

### Contribution Margin Calculation
| Channel | Sell Price | All Costs | Contribution | Margin % |
|---------|------------|-----------|--------------|----------|
| Website | £8.99 | £6.24 | £2.75 | 30.6% |
| Amazon FBA | £8.99 | £10.88 | -£1.89 | -21.0% |
| Amazon FBM | £8.99 | £7.50 | £1.49 | 16.6% |
| eBay | £8.99 | £7.50 | £1.49 | 16.6% |
```

#### 2.2 Margin Targets by Category

Define target margins based on category dynamics:

```markdown
## Target Margin Matrix

| Category | Target Margin | Min Acceptable | Max (Premium) |
|----------|---------------|----------------|---------------|
| Cable Ties | 30% | 20% | 40% |
| Fixings & Fasteners | 35% | 25% | 45% |
| Hand Tools | 35% | 25% | 50% |
| Power Tools | 25% | 15% | 35% |
| Safety/PPE | 40% | 30% | 50% |
| Consumables | 35% | 25% | 45% |
| Storage | 30% | 20% | 40% |
| Speciality | 45% | 35% | 60% |

### Factors Affecting Target:
- **Higher margin justified:** Unique product, less competition, high service element
- **Lower margin acceptable:** High volume, loss leader, strategic entry
```

#### 2.3 Price Floor Calculation

Calculate minimum viable price per channel:

```markdown
## Price Floor Formula

Price Floor = (Landed Cost + Variable Costs + Channel Fees) / (1 - Min Margin)

### Example: Cable Ties on Amazon FBA
Landed Cost: £2.45
Variable Costs: £0.50 (picking only, FBA handles rest)
Channel Fees: £4.64 (referral + FBA)
Min Margin: 15%

Price Floor = (£2.45 + £0.50 + £4.64) / (1 - 0.15)
Price Floor = £7.59 / 0.85
Price Floor = £8.93

### Summary by Channel:
| Channel | Price Floor | Current Price | Status |
|---------|-------------|---------------|--------|
| Website | £5.85 | £8.99 | ✅ Above floor |
| Amazon FBA | £8.93 | £8.99 | ⚠️ Marginal |
| eBay | £6.72 | £8.99 | ✅ Above floor |
```

#### 2.4 Portfolio Margin Analysis

Analyze margins across entire catalog:

```markdown
## Portfolio Health Check

### By Margin Band:
| Margin Band | SKU Count | % of SKUs | Revenue % |
|-------------|-----------|-----------|-----------|
| Negative (loss) | 23 | 4% | 2% |
| 0-15% (marginal) | 89 | 15% | 12% |
| 15-25% (acceptable) | 178 | 30% | 35% |
| 25-35% (target) | 201 | 34% | 38% |
| 35-50% (healthy) | 89 | 15% | 11% |
| 50%+ (premium) | 12 | 2% | 2% |

### Action Plan:
1. **Negative margin SKUs:** Review for price increase or discontinuation
2. **Marginal SKUs:** Evaluate competitive necessity vs. profitability
3. **Below target:** Identify quick-win price increase candidates
```

**Tools:** Spreadsheet model, ERP cost data, channel fee calculators

**Output:** Margin analysis document with pricing recommendations

---

### Step 3: Promotional Calendar Planning

**What:** Plan promotional pricing strategically throughout the year.

**How:**

#### 3.1 Promotional Calendar Framework

```markdown
## Annual Promotional Calendar

### Q1 (January - March)
| Event | Dates | Type | Discount | Categories | Goal |
|-------|-------|------|----------|------------|------|
| New Year Sale | Jan 2-15 | Site-wide | 15% | All | Clear winter stock |
| Trade Account Push | Feb | Targeted | 20% | Tools | B2B acquisition |
| Spring Prep | Mar | Category | 10-20% | Garden, Outdoor | Seasonal prep |

### Q2 (April - June)
| Event | Dates | Type | Discount | Categories | Goal |
|-------|-------|------|----------|------------|------|
| Easter Sale | Apr | Site-wide | 10% | All | Momentum |
| Trade Show | May | Event | 25% | Show specials | Lead gen |
| Father's Day | Jun | Category | 15% | Tools, Gadgets | Gift sales |

### Q3 (July - September)
| Event | Dates | Type | Discount | Categories | Goal |
|-------|-------|------|----------|------------|------|
| Summer Sale | Jul | Site-wide | 15% | All | Clear summer stock |
| Back to Work | Sep | B2B | 10% | Office/Trade | Post-summer push |
| Amazon Prime Day | Jul* | Amazon | 20-30% | Top sellers | Visibility |

### Q4 (October - December)
| Event | Dates | Type | Discount | Categories | Goal |
|-------|-------|------|----------|------------|------|
| Black Friday | Nov 24-27 | Site-wide | 20-30% | All | Major revenue |
| Cyber Monday | Nov 27 | Online only | 25% | Tech, Tools | Digital push |
| Christmas Sale | Dec 1-23 | Site-wide | 15% | Gift items | Holiday |
| Post-Xmas | Dec 26+ | Clearance | 30-50% | Excess stock | Liquidation |

### Monthly Recurring
- First Monday: Flash sale email (24hr, category rotation)
- 15th: Trade account exclusive offer
- End of month: Stock clearance page refresh
```

#### 3.2 Promotion Types & Mechanics

```markdown
## Promotion Mechanics

### Percentage Discount
**Use when:** General sales, site-wide events
**Format:** "15% off everything" or "20% off Tools"
**Margin impact:** Direct hit to margin
**Best for:** B2C, impulse purchases

### Money-Off Threshold
**Use when:** Increasing AOV
**Format:** "£10 off orders over £50" or "£25 off £100+"
**Margin impact:** Predictable per-order discount
**Best for:** Trade, bulk buyers

### Bundle Deals
**Use when:** Moving slow movers, increasing units
**Format:** "Buy 2 get 1 free" or "3 for £20"
**Margin impact:** Depends on mix
**Best for:** Consumables, low ASP items

### Free Shipping
**Use when:** Competing with Prime, reducing friction
**Format:** "Free shipping on £35+" or "Free next-day on £75+"
**Margin impact:** Shipping cost absorption
**Best for:** All segments

### Buy More Save More
**Use when:** Driving quantity per order
**Format:** "1 for £10, 2 for £18, 3 for £25"
**Margin impact:** Graduated, encourages upsell
**Best for:** Consumables, trade buyers

### Flash Sales
**Use when:** Creating urgency, clearing stock
**Format:** "24 hours only: 30% off [category]"
**Margin impact:** Steep but short
**Best for:** Email list engagement, clearance
```

#### 3.3 Promotional Profitability Planning

Before launching any promotion:

```markdown
## Promotion Planning Template

### Promotion: Black Friday 2024
**Dates:** Nov 24-27 (4 days)
**Discount:** 20% site-wide

### Financial Forecast
| Metric | Normal Period | Promo Period | Change |
|--------|---------------|--------------|--------|
| Daily orders | 85 | 340 | +300% |
| Average order value | £45 | £62 | +38% |
| Daily revenue | £3,825 | £21,080 | +451% |
| Gross margin | 35% | 23% | -12pp |
| Daily contribution | £1,339 | £4,848 | +262% |

### 4-Day Totals
| Metric | Amount |
|--------|--------|
| Total revenue | £84,320 |
| Total margin | £19,394 |
| Discount cost | £21,080 |
| Incremental profit | £8,700 |

### Break-Even Analysis
Need to increase orders by: 71% to maintain absolute profit
Expected increase: 300%
Profitable: ✅ Yes

### Stock Requirements
| Product | Normal Demand | Promo Demand | Stock Check |
|---------|---------------|--------------|-------------|
| Cable Ties | 200 | 800 | ✅ 1,500 in stock |
| Screw Sets | 50 | 200 | ⚠️ Order 100 more |
| Safety Glasses | 30 | 120 | ❌ Only 80, limit or exclude |
```

**Tools:** Promotional calendar, profitability model, stock checker

**Output:** Annual promotional calendar with profitability forecasts

---

### Step 4: Bundle Pricing Strategies

**What:** Create product bundles that increase AOV and margin while providing customer value.

**How:**

#### 4.1 Bundle Strategy Types

```markdown
## Bundle Strategy Matrix

### Pure Bundle
All products only sold together
- Example: "Complete Electrician Starter Kit" (cannot buy components separately)
- Pros: Higher perceived value, simple
- Cons: Less flexibility

### Mixed Bundle
Products available individually AND as bundle
- Example: Cable ties + clips sold separately or as "Cable Management Kit"
- Pros: Captures all buyers
- Cons: Can cannibalize individual sales

### Cross-Category Bundle
Products from different categories bundled
- Example: Tools + Safety Equipment + Consumables = "New Contractor Kit"
- Pros: Introduces customers to new categories
- Cons: Complex to manage

### Complementary Bundle
Products that enhance each other
- Example: Drill + Drill Bits + Case
- Pros: Natural pairing, genuine value
- Cons: Customers may already own components

### Volume Bundle
Same product in larger quantities
- Example: Cable Ties 100-pack vs 500-pack vs 1000-pack
- Pros: Simple, encourages larger orders
- Cons: Price architecture complexity
```

#### 4.2 Bundle Pricing Models

```markdown
## Bundle Pricing Calculations

### Cost-Plus Bundle Pricing
Bundle Price = Sum of Costs × (1 + Bundle Margin Target)

Example:
- Item A cost: £5.00
- Item B cost: £3.00
- Item C cost: £2.00
- Total cost: £10.00
- Target margin: 35%
- Bundle price: £10.00 × 1.35 = £13.50

### Value-Based Bundle Pricing
Bundle Price = Sum of Individual Prices × (1 - Bundle Discount)

Example:
- Item A price: £12.99
- Item B price: £8.99
- Item C price: £5.99
- Total if bought separately: £27.97
- Bundle discount: 15%
- Bundle price: £27.97 × 0.85 = £23.77

### Competitive Bundle Pricing
Bundle Price = Competitor Bundle Price × Position Factor

Example:
- Competitor bundle: £29.99
- Our position: Value leader (-10%)
- Our bundle price: £26.99

### Psychology-Based Pricing
| Individual Total | Bundle Price | Perceived Saving | Psychology |
|------------------|--------------|------------------|------------|
| £27.97 | £23.99 | £3.98 (14%) | "Save almost £4" |
| £27.97 | £24.99 | £2.98 (11%) | "Under £25" |
| £27.97 | £21.97 | £6.00 (21%) | "Save over £6" |
```

#### 4.3 Bundle Examples for GTSE

```markdown
## GTSE Bundle Offerings

### Bundle 1: Cable Management Pro Kit
**Contains:**
- Cable Ties 300mm x 100 (RRP £8.99)
- Cable Ties 200mm x 100 (RRP £6.99)
- Self-Adhesive Cable Clips x 100 (RRP £6.99)
- Cable Tie Gun (RRP £12.99)
- Velcro Cable Ties x 50 (RRP £7.99)

**Pricing:**
- Individual total: £43.95
- Bundle price: £34.99
- Saving: £8.96 (20%)
- Our margin: 32% (vs 35% individual)

**Positioning:** "Everything you need for professional cable management"

### Bundle 2: Electrician Essentials
**Contains:**
- VDE Screwdriver Set (RRP £34.99)
- Voltage Tester (RRP £15.99)
- Electrical Tape 10-pack (RRP £8.99)
- Cable Ties Assortment (RRP £14.99)
- Safety Glasses (RRP £4.99)

**Pricing:**
- Individual total: £79.95
- Bundle price: £64.99
- Saving: £14.96 (19%)
- Our margin: 29% (vs 34% individual)

**Positioning:** "Start every job prepared"

### Bundle 3: Trade Starter Pack
**Contains:**
- Screw Assortment 1000pc (RRP £29.99)
- Wall Plug Assortment (RRP £12.99)
- Drill Bit Set (RRP £24.99)
- Fixings Organizer Box (RRP £14.99)

**Pricing:**
- Individual total: £82.96
- Bundle price: £69.99
- Saving: £12.97 (16%)
- Our margin: 31% (vs 36% individual)

**Positioning:** "The essential fixings kit for any tradesperson"
```

#### 4.4 Bundle Performance Tracking

```markdown
## Bundle Performance Dashboard

| Bundle Name | Units/Month | Revenue | Margin | AOV Impact |
|-------------|-------------|---------|--------|------------|
| Cable Management Pro | 45 | £1,575 | 32% | +£18 vs avg |
| Electrician Essentials | 28 | £1,820 | 29% | +£41 vs avg |
| Trade Starter Pack | 62 | £4,340 | 31% | +£35 vs avg |

### Cannibalization Check
| Product | Solo Sales Before | Solo Sales After | Bundle Sales | Net Change |
|---------|-------------------|------------------|--------------|------------|
| Cable Ties 300mm | 320 | 280 | 45 | +5 units |
| VDE Screwdriver Set | 85 | 65 | 28 | +8 units |

### Bundle Optimization Actions
1. Electrician Essentials margin low → consider removing Voltage Tester
2. Cable Management highly successful → create "Pro Plus" version
3. Test: Add "Build Your Own Bundle" configurator
```

**Tools:** Bundle pricing calculator, performance tracker

**Output:** Bundle strategy document with specific offerings and pricing

---

### Step 5: B2B Tier Pricing Logic

**What:** Create a tiered pricing structure for B2B trade customers based on volume, loyalty, and relationship value.

**How:**

#### 5.1 B2B Tier Structure

```markdown
## Trade Account Tier Structure

### Tier Definitions

| Tier | Annual Spend | Discount | Payment Terms | Benefits |
|------|--------------|----------|---------------|----------|
| Bronze | £0-2,499 | 10% | 14 days | Basic trade pricing |
| Silver | £2,500-9,999 | 15% | 30 days | + Free delivery £35+ |
| Gold | £10,000-24,999 | 20% | 30 days | + Free next-day, priority support |
| Platinum | £25,000+ | 25%+ | 45 days | + Account manager, custom terms |

### Tier Movement Rules
- Review period: Quarterly
- Upgrade: Immediate upon hitting threshold
- Downgrade: After 2 consecutive quarters below threshold
- Grace period: 90 days after downgrade warning
```

#### 5.2 Discount Implementation

```markdown
## B2B Discount Logic

### Method 1: Percentage Off RRP
Trade Price = RRP × (1 - Tier Discount)

Example (Gold Tier, 20% off):
- RRP: £8.99
- Trade Price: £8.99 × 0.80 = £7.19

### Method 2: Category-Variable Discounts
Different discounts by category based on margin room:

| Category | Bronze | Silver | Gold | Platinum |
|----------|--------|--------|------|----------|
| Cable Ties | 10% | 15% | 20% | 25% |
| Hand Tools | 8% | 12% | 18% | 22% |
| Power Tools | 5% | 8% | 12% | 15% |
| Safety/PPE | 12% | 18% | 25% | 30% |
| Speciality | 15% | 20% | 28% | 35% |

### Method 3: Volume-Based Additional Discount
Base tier discount + volume bonus:

| Order Value | Additional Discount |
|-------------|---------------------|
| £0-99 | 0% |
| £100-249 | +2% |
| £250-499 | +3% |
| £500-999 | +5% |
| £1,000+ | +7% (or negotiated) |

Example:
- Gold customer (20% base)
- Orders £600 worth
- Gets 20% + 5% = 25% off that order
```

#### 5.3 Trade Price List Generation

```markdown
## Trade Price List Format

### GTSE TRADE PRICE LIST - GOLD TIER
Valid: [Date] to [Date]

| SKU | Description | Unit | RRP | Your Price | Saving |
|-----|-------------|------|-----|------------|--------|
| CT300BK100 | Cable Ties 300mm Black x100 | Pack | £8.99 | £7.19 | £1.80 |
| CT200NA100 | Cable Ties 200mm Natural x100 | Pack | £6.99 | £5.59 | £1.40 |
| WSA440-500 | Wood Screws 4x40mm x500 | Box | £19.99 | £15.99 | £4.00 |
| VDE-SET-8 | VDE Screwdriver Set 8pc | Set | £34.99 | £27.99 | £7.00 |
| ... | | | | | |

### Notes:
- Prices exclude VAT
- Free delivery on orders over £35
- 30-day payment terms
- Volume discounts available on orders £500+
```

#### 5.4 B2B Quoting Process

```markdown
## Quote Generation Process

### Standard Quote (within tier pricing)
1. Customer requests quote
2. System generates based on tier discount
3. Auto-approve if within parameters
4. Valid for 30 days

### Custom Quote (outside standard terms)
Approval matrix:

| Request Type | Approval Level | Max Deviation |
|--------------|----------------|---------------|
| Extra 5% discount | Sales Rep | Up to 5% additional |
| Extra 5-10% discount | Sales Manager | Up to 10% additional |
| Extra 10%+ discount | Director | Case by case |
| Extended terms | Finance Manager | Up to 60 days |
| Credit limit increase | Finance Director | Based on credit check |

### Quote Template
```
GTSE QUOTATION #[NUMBER]
Date: [DATE]
Valid Until: [DATE + 30]
Customer: [COMPANY]
Account: [TIER]

| Qty | SKU | Description | Unit Price | Line Total |
|-----|-----|-------------|------------|------------|
| 10 | CT300BK100 | Cable Ties 300mm | £6.50 | £65.00 |
| 5 | WSA440-500 | Wood Screws | £14.99 | £74.95 |

Subtotal: £139.95
Discount Applied: Gold (20%) + Volume 5% = 25%
Your Price: £104.96
VAT: £20.99
Total: £125.95

Terms: 30 days from invoice date
Delivery: Free next-day (orders over £35)
```
```

#### 5.5 Tier Migration Communications

```markdown
## Tier Change Email Templates

### Upgrade Notification

Subject: Congratulations! You've been upgraded to [Gold] Tier 🎉

Hi [Name],

Great news! Based on your orders over the past quarter, you've been upgraded to GTSE [Gold] Tier.

What this means for you:
✓ [20%] discount on all products (was [15%])
✓ [30-day] payment terms (was [14-day])
✓ Free next-day delivery on all orders
✓ Priority customer support line

Your new pricing is effective immediately.

[VIEW YOUR NEW PRICE LIST →]

Thank you for your continued business!

---

### Downgrade Warning (60-day notice)

Subject: Important: Your GTSE account tier status

Hi [Name],

We wanted to let you know that your account is currently below the [Gold] tier spending threshold.

Current period spend: £[X,XXX]
[Gold] tier requirement: £[10,000] annually (£2,500/quarter)

If spending remains below threshold for 2 consecutive quarters, your account will be adjusted to [Silver] tier on [Date].

What you can do:
- Place orders before [Date] to maintain tier
- Speak to your account manager about annual commitments
- Consolidate purchases to maximize tier benefits

We're here to help. Call [Number] or reply to discuss.
```

**Tools:** ERP/CRM tier logic, quote generator, email automation

**Output:** Complete B2B pricing structure with tier rules and communications

---

### Step 6: Amazon Pricing Rules

**What:** Navigate Amazon's pricing requirements while maintaining profitability.

**How:**

#### 6.1 Amazon Pricing Requirements

```markdown
## Amazon Pricing Rules

### Price Parity Policy
Amazon expects competitive pricing:
- Price should not be higher than other online channels
- Amazon uses bots to detect price differences
- Violations can result in Buy Box loss or listing suppression

### Fair Pricing Policy
Amazon will suppress listings with prices:
- Significantly higher than recent prices
- Higher than recently set reference prices
- That appear to be price gouging during demand spikes

### Reference Price Rules (RRP/Was Price)
To show "Was £X, Now £Y":
- Must have sold at "Was" price recently
- Must have sold for "Was" price for meaningful period
- Can't inflate "Was" price artificially

### Buy Box Considerations
Price is not the only factor:
- Fulfillment method (FBA generally wins)
- Seller metrics (feedback, ODR)
- Shipping speed and cost
- Stock availability
```

#### 6.2 Amazon Pricing Strategy

```markdown
## Amazon Channel Strategy

### Option 1: Price Match Website
**Strategy:** Amazon price = Website price
**Pros:** Simple, compliant, consistent
**Cons:** May lose margin due to Amazon fees

**Margin calculation:**
| | Website | Amazon FBA |
|---------------|---------|------------|
| Sell price | £8.99 | £8.99 |
| Product cost | £2.45 | £2.45 |
| Variable costs | £3.79 | £0.50 |
| Channel fees | £0.00 | £4.64 |
| Net margin | £2.75 (30.6%) | £1.40 (15.6%) |

### Option 2: Amazon Premium
**Strategy:** Amazon price slightly higher (justify with Prime/convenience)
**Pros:** Protects margin
**Cons:** May lose Buy Box to competitors

**Example:**
- Website: £8.99
- Amazon: £9.99 (+11%)
- Justification: Prime next-day vs standard delivery

### Option 3: Amazon-Specific SKUs
**Strategy:** Create differentiated products for Amazon
**Pros:** Avoids price comparison, maintains both margins
**Cons:** Complexity, inventory management

**Example:**
- Website: Cable Ties 300mm x100 @ £8.99
- Amazon: Cable Ties 300mm x150 (Amazon Exclusive) @ £12.99
  - Different pack size = not comparable
  - Better margin per unit

### Option 4: Amazon Loss Leader
**Strategy:** Accept lower Amazon margin for visibility
**Pros:** Customer acquisition, reviews, brand building
**Cons:** Lower profitability

**When to use:**
- New product launches (90 days)
- Fighting for category leadership
- When Amazon drives significant volume
```

#### 6.3 Amazon Repricing Rules

```markdown
## Repricing Strategy

### Automated Repricing Rules

**Rule 1: Price Floor Protection**
Never go below: [Landed Cost + Min Margin]
Override: Manual only

**Rule 2: Compete for Buy Box**
When Buy Box lost:
- If within 3%, match lowest FBA price
- If 3-5% gap, reduce by 2%
- If >5% gap, hold position (review manually)

**Rule 3: Maximize When Winning**
When holding Buy Box:
- Test 2% increase
- If still winning after 24hr, test another 2%
- Maximum increase from floor: 15%

**Rule 4: Low Competition Response**
When <3 FBA sellers:
- Increase price by 5%
- Monitor Buy Box retention

### Manual Review Triggers
| Situation | Action |
|-----------|--------|
| New competitor significantly undercuts | Review costs, consider matching or exiting |
| Category-wide price increase | Follow market up |
| Stock running low | Consider price increase |
| Competitor out of stock | Opportunity to increase |
| Post-Prime Day | Return to normal pricing |
```

#### 6.4 Cross-Channel Consistency

```markdown
## Multi-Channel Price Management

### Price Hierarchy
1. **Website (Base):** Full control, best margin
2. **Amazon:** Match or premium based on strategy
3. **eBay:** Typically matches Amazon
4. **Google Shopping:** Feeds from website
5. **Trade Portal:** B2B pricing (separate)

### Consistency Rules
| Scenario | Website | Amazon | eBay | Trade |
|----------|---------|--------|------|-------|
| Normal | £8.99 | £8.99 | £9.49 | £7.19 (Gold) |
| Site Sale | £7.64 (-15%) | £8.99 (hold) | £9.49 | £7.19 |
| Amazon Sale | £8.99 | £7.64 (-15%) | £7.64 | £7.19 |
| Black Friday | £7.19 (-20%) | £7.19 | £7.19 | £6.29 (extra 10%) |

### Avoiding Parity Violations
1. Run website sales as "member only" (login required)
2. Use coupon codes rather than visible price drops
3. Ensure Google Shopping feed doesn't show sale prices that violate Amazon rules
4. Communicate with Amazon support if running legitimate sales
```

**Tools:** Amazon Seller Central, Repricing software, Feed management

**Output:** Amazon pricing strategy document with repricing rules

---

### Step 7: Dynamic Pricing Implementation

**What:** Implement data-driven dynamic pricing that responds to market conditions.

**How:**

#### 7.1 Dynamic Pricing Factors

```markdown
## Dynamic Pricing Variables

### Demand Signals
| Signal | Impact | Weight |
|--------|--------|--------|
| High demand (velocity up) | Price increase | 20% |
| Low demand (velocity down) | Price decrease | 15% |
| Seasonal peak | Price increase | 15% |
| Seasonal trough | Price decrease | 10% |

### Competition Signals
| Signal | Impact | Weight |
|--------|--------|--------|
| Competitor price drop | Consider matching | 25% |
| Competitor out of stock | Price increase opportunity | 15% |
| New competitor enters | Defensive pricing | 20% |
| Competitor exits | Price increase opportunity | 10% |

### Inventory Signals
| Signal | Impact | Weight |
|--------|--------|--------|
| Low stock (<2 weeks) | Price increase or hold | 20% |
| Overstock (>6 months) | Price decrease | 20% |
| New stock incoming | Prepare for promotion | 10% |
| Dead stock (>12 months) | Aggressive clearance | 25% |

### External Signals
| Signal | Impact | Weight |
|--------|--------|--------|
| Cost increase from supplier | Price increase | 100% pass-through |
| Currency fluctuation | Adjust if >5% | Proportional |
| Shipping cost changes | Adjust thresholds | Proportional |
| Tariff changes | Price increase | 100% pass-through |
```

#### 7.2 Price Change Rules

```markdown
## Price Change Governance

### Automatic Changes (No approval needed)
- Within ±5% of current price
- Matching competitor who dropped price
- Staying above margin floor
- Repricer rules within parameters

### Require Manager Approval
- Price changes >5%
- New product pricing
- Changes to pricing strategy
- Promotional pricing

### Require Director Approval
- Pricing below margin floor
- Strategic loss leaders
- Major category repricing
- Customer-specific contracts

### Price Change Frequency
| Product Type | Max Changes | Review Period |
|--------------|-------------|---------------|
| Commodity | Daily | Weekly |
| Standard | Weekly | Monthly |
| Premium | Monthly | Quarterly |
| Speciality | Quarterly | Annually |

### Price Change Log
| Date | SKU | Old | New | Reason | Approved By |
|------|-----|-----|-----|--------|-------------|
| 15/01 | CT300 | £8.99 | £9.49 | Competitor matched | Auto |
| 16/01 | VDE-8 | £34.99 | £32.99 | Slow velocity | J.Smith |
| 17/01 | DRILL01 | £49.99 | £44.99 | Overstock | Director |
```

#### 7.3 Price Testing Framework

```markdown
## A/B Price Testing

### Test Setup
**Product:** Cable Ties 300mm Black
**Current price:** £8.99
**Test prices:** £8.49, £9.49
**Duration:** 2 weeks
**Split:** 33% each

### Test Results
| Price | Sessions | Conversion | Revenue | Margin | Profit |
|-------|----------|------------|---------|--------|--------|
| £8.49 | 1,000 | 4.8% | £408 | 26% | £106 |
| £8.99 | 1,000 | 4.2% | £378 | 30% | £113 |
| £9.49 | 1,000 | 3.5% | £332 | 34% | £113 |

### Decision
Profit maximized at £8.99 (current) and £9.49 (equal)
Recommendation: Increase to £9.49 (same profit, lower volume servicing cost)

### Implementation
- Increase price to £9.49
- Monitor for 2 weeks
- Rollback if conversion drops >20%
```

**Tools:** A/B testing platform, analytics, dynamic pricing software

**Output:** Dynamic pricing system with rules and testing framework

---

## Examples

### Example 1: New Product Pricing

**Product:** GTSE Professional Cable Tie Gun

**Step 1: Cost Analysis**
- Landed cost: £4.50
- Target margin: 35%
- Minimum price: £6.92

**Step 2: Competitor Analysis**
| Competitor | Product | Price |
|------------|---------|-------|
| Amazon (various) | Generic cable tie gun | £8.99-14.99 |
| Toolstation | Cable tie tensioner | £12.99 |
| Screwfix | Cable tie tool | £15.99 |

**Step 3: Positioning Decision**
- Position: Value leader (quality at competitive price)
- Target price point: £12.99

**Step 4: Margin Check**
- Price: £12.99
- Costs: £7.50 (incl. variable)
- Margin: 42% ✅

**Step 5: Channel Pricing**
| Channel | Price | Margin |
|---------|-------|--------|
| Website | £12.99 | 42% |
| Amazon FBA | £14.99 | 26% |
| Trade (Gold) | £10.39 | 28% |

**Step 6: Launch Promotion**
- First 30 days: £10.99 (15% off)
- Include in bundle: Cable Management Pro Kit

---

### Example 2: Promotional Pricing Analysis

**Scenario:** Planning Black Friday promotion

**Current State:**
- Category: All products
- Average margin: 35%
- Average daily revenue: £4,200

**Promotion Options Analysis:**

| Discount | Est. Volume Lift | Revenue | Margin | Profit |
|----------|------------------|---------|--------|--------|
| 10% | +50% | £5,670 | 25% | £1,418 |
| 15% | +100% | £7,140 | 20% | £1,428 |
| 20% | +180% | £9,072 | 15% | £1,361 |
| 25% | +220% | £9,660 | 10% | £966 |

**Optimal choice:** 15% discount
- Highest absolute profit
- Sustainable margin
- Significant volume lift

**Selected approach:**
- Site-wide 15% with code BLACKFRIDAY
- Top 20 products at 25% (