---
name: b2b-account-penetration
title: B2B Account Penetration & Growth
description: Systematic approach to growing existing B2B customer accounts through analysis, relationship building, and strategic expansion
version: 1.0.0
tags: [b2b, account-management, customer-growth, cross-sell, upsell]
---

# B2B Account Penetration & Growth

## Purpose

This skill provides a systematic methodology for identifying and executing growth opportunities within existing B2B customer accounts. Rather than focusing solely on new customer acquisition, this approach maximizes value from your established customer base through deeper relationships, broader product penetration, and strategic account planning.

**Use this skill when:**
- An existing customer hasn't ordered in 30+ days
- You want to expand product categories sold to an account
- Preparing for a Quarterly Business Review (QBR)
- A customer's order frequency or value has declined
- You've identified a high-potential account for expansion
- Onboarding a new account manager to existing accounts

**GTSE Context:** For trade and industrial supply companies like GTSE, B2B customers represent the majority of revenue. Growing wallet share with existing accounts is 5-7x more cost-effective than acquiring new customers. This skill is optimized for product distributors selling consumables, tools, and supplies.

## Inputs

- `account_name`: Company name (e.g., "ABC Electrical Contractors Ltd")
- `account_id`: Internal customer ID / account number
- `primary_contact`: Main contact name and role
- `account_history`: Access to order history data
- `product_catalog`: Full product catalog for cross-sell reference
- `account_tier`: Current customer tier (Bronze/Silver/Gold/Platinum)
- `last_order_date`: Most recent order date

## Prerequisites

Before starting this skill, ensure you have:

1. **Access to Customer Data**
   - Order history (minimum 12 months)
   - Contact information for all stakeholders
   - Previous communications/notes

2. **Product Knowledge**
   - Full understanding of product catalog
   - Cross-sell/upsell relationships defined
   - Pricing tiers and discount structures

3. **Account Management Tools**
   - CRM system access
   - Email marketing platform
   - Order management system

4. **Internal Resources**
   - Authority to offer discounts/terms
   - Technical support availability
   - Sample/trial product availability

---

## Procedure

### Step 1: Account Health Assessment

**What:** Evaluate current account status to identify immediate risks and opportunities.

**How:**

#### 1.1 Pull Account Metrics

Generate the following report for the past 12 months:

```markdown
## Account Health Report: [Company Name]

### Basic Information
- Account Number: 
- Primary Contact: 
- Contact Email/Phone:
- Address:
- Account Age: X years
- Account Tier: 
- Credit Terms:
- Credit Limit:

### Order History Summary
| Period | Orders | Revenue | Avg Order Value | Products |
|--------|--------|---------|-----------------|----------|
| This Month | X | £X,XXX | £XXX | XX |
| Last Month | X | £X,XXX | £XXX | XX |
| Last Quarter | X | £X,XXX | £XXX | XX |
| Last 12 Months | X | £XX,XXX | £XXX | XX |
| Prior 12 Months | X | £XX,XXX | £XXX | XX |

### Year-over-Year Change
- Revenue: +/- XX%
- Order Frequency: +/- XX%
- Average Order Value: +/- XX%
```

#### 1.2 Calculate Health Score

Score each factor 1-5 (1 = at risk, 5 = excellent):

| Factor | Weight | Score | Weighted Score |
|--------|--------|-------|----------------|
| Order recency (last order) | 25% | /5 | |
| Order frequency trend | 20% | /5 | |
| Revenue trend | 20% | /5 | |
| Product diversity | 15% | /5 | |
| Engagement (responses, calls) | 10% | /5 | |
| Payment reliability | 10% | /5 | |
| **Total** | 100% | | /5.0 |

**Scoring Guide - Order Recency:**
- 5: Ordered in last 7 days
- 4: Ordered in last 14 days
- 3: Ordered in last 30 days
- 2: Ordered in last 60 days
- 1: No order in 60+ days

**Scoring Guide - Revenue Trend (YoY):**
- 5: Growth >20%
- 4: Growth 10-20%
- 3: Stable (-10% to +10%)
- 2: Decline 10-30%
- 1: Decline >30%

**Health Score Interpretation:**
- **4.0-5.0:** Healthy - Focus on expansion
- **3.0-3.9:** Stable - Identify growth opportunities
- **2.0-2.9:** At Risk - Immediate outreach needed
- **1.0-1.9:** Critical - Escalate to management

#### 1.3 Risk Identification

Check for warning signs:

| Warning Sign | Present? | Action |
|--------------|----------|--------|
| No order in 45+ days | Y/N | Immediate outreach |
| Order value down >20% | Y/N | Price/product review |
| Switched product categories | Y/N | Investigate competitor |
| Late payments increasing | Y/N | Credit review |
| Contact not responding | Y/N | Find new contact |
| Complaints/returns increasing | Y/N | Quality review |

**Tools:** CRM, Order Management System, Excel/Google Sheets

**Output:** Completed Account Health Report with score and risk flags

---

### Step 2: Purchase History Analysis

**What:** Deep dive into what the customer buys to identify patterns, gaps, and opportunities.

**How:**

#### 2.1 Category Analysis

Break down purchases by product category:

```markdown
## Purchase Breakdown: [Company Name]

### By Category (Last 12 Months)
| Category | Revenue | % of Total | Units | Avg Unit Price |
|----------|---------|------------|-------|----------------|
| Cable Ties | £4,200 | 42% | 8,400 | £0.50 |
| Fixings & Fasteners | £2,800 | 28% | 14,000 | £0.20 |
| Hand Tools | £1,500 | 15% | 25 | £60.00 |
| Electrical | £800 | 8% | 400 | £2.00 |
| Safety & PPE | £700 | 7% | 350 | £2.00 |
| **Total** | **£10,000** | **100%** | | |

### Categories NOT Purchased (Opportunity)
| Category | Est. Market Size | Competition | Priority |
|----------|-----------------|-------------|----------|
| Power Tools | High | Strong | Medium |
| Consumables | High | Weak | High |
| Storage & Organization | Medium | Weak | High |
| Lighting | Medium | Medium | Medium |
```

#### 2.2 Product-Level Analysis

For their top 10 products, identify:

```markdown
### Top 10 Products Purchased

| Rank | Product | SKU | Units (12mo) | Revenue | Last Order | Reorder Period |
|------|---------|-----|--------------|---------|------------|----------------|
| 1 | Cable Ties 300mm Black | CT300BK | 4,000 | £2,000 | 5 days ago | 14 days |
| 2 | Cable Ties 200mm Natural | CT200NA | 3,000 | £1,200 | 12 days ago | 21 days |
| 3 | Wood Screws 4x40 | WS440 | 10,000 | £800 | 8 days ago | 30 days |
| ... | | | | | | |
```

#### 2.3 Buying Pattern Analysis

Identify ordering patterns:

**Frequency Analysis:**
```
Average days between orders: 18 days
Median order size: £185
Order size range: £45 - £820
Peak ordering days: Tuesday, Thursday
Peak ordering months: March, September
```

**Seasonality:**
| Month | Revenue | Index (vs avg) |
|-------|---------|----------------|
| Jan | £650 | 78 |
| Feb | £720 | 86 |
| Mar | £1,100 | 132 |
| Apr | £920 | 110 |
| ... | | |

#### 2.4 Churn Risk by Product

Identify products they've stopped buying:

```markdown
### Products Previously Purchased, Now Dormant

| Product | Last Ordered | Previous 12mo | Prior 12mo | Churn Risk |
|---------|--------------|---------------|------------|------------|
| Drill Bits Set | 8 months ago | £0 | £340 | High |
| Safety Goggles | 6 months ago | £45 | £180 | Medium |
| Tape Measure | 4 months ago | £0 | £85 | Medium |
```

**Possible Reasons:**
- Switched to competitor
- Project ended
- Found alternative product
- Stockpiled previously

**Tools:** Order history export, Excel pivot tables, CRM

**Output:** Complete purchase analysis with opportunity matrix

---

### Step 3: Cross-Sell & Upsell Identification

**What:** Match customer needs with products they're not currently buying from you.

**How:**

#### 3.1 Product Affinity Analysis

Based on what they buy, identify logical cross-sells:

```markdown
## Cross-Sell Matrix: [Company Name]

### Current Purchases → Recommended Products

| They Buy | Consider Selling | Rationale | Priority |
|----------|-----------------|-----------|----------|
| Cable Ties | Cable Tie Gun | Increases efficiency | High |
| Cable Ties | Cable Clips | Complementary | Medium |
| Cable Ties | Spiral Wrap | Alternative cable management | Medium |
| Wood Screws | Screw Bit Sets | Required for use | High |
| Wood Screws | Countersink Bits | Common pairing | High |
| Hand Tools | Tool Bags/Cases | Storage need | Medium |
| Electrical | Cable Cutters | Required tool | High |
| Electrical | Insulation Tape | Consumable need | High |
```

#### 3.2 Product Line Gaps

Identify product lines where they buy some but not all:

```markdown
### Incomplete Product Lines

**Cable Ties (Currently buying 2 of 8 variants):**
- ✅ 300mm Black (buying)
- ✅ 200mm Natural (buying)
- ❌ 100mm Black (not buying)
- ❌ 200mm Black (not buying)
- ❌ 370mm Black (not buying)
- ❌ 4.8mm Heavy Duty (not buying)
- ❌ Releasable Cable Ties (not buying)
- ❌ Coloured Cable Ties (not buying)

**Opportunity:** £800-1,200/year estimated if full range adopted
**Approach:** Send sample pack of variants not purchased
```

#### 3.3 Upsell Opportunities

Identify premium alternatives to current purchases:

```markdown
### Upsell Candidates

| Current Product | Premium Alternative | Price Diff | Value Proposition |
|-----------------|---------------------|------------|-------------------|
| Standard Cable Ties | Heavy Duty Cable Ties | +25% | Higher tensile strength |
| Yellow Zinc Screws | Stainless Steel | +100% | Outdoor durability |
| Basic Hand Tools | Professional Grade | +50% | Lifetime warranty |
| Standard PPE | Premium PPE | +35% | Comfort for all-day wear |
```

#### 3.4 Competitor Displacement

Identify products they likely buy elsewhere:

```markdown
### Competitor Displacement Targets

Based on their business type (Electrical Contractor), they likely need:

| Product Category | Our Product | Key Competitors | Win Strategy |
|------------------|-------------|-----------------|--------------|
| Test Equipment | Voltage Testers | Fluke, Klein | Price + Service |
| Cable Cutters | Pro Cable Cutters | Knipex, Wiha | Bundle deal |
| First Aid | First Aid Kits | HSE Direct | Convenience |
| Consumables | Tape, Markers | Toolstation | Consolidate orders |
```

**Tools:** Product catalog, affinity mapping, CRM notes

**Output:** Prioritized cross-sell/upsell opportunity list (5-10 items)

---

### Step 4: Relationship Mapping

**What:** Understand all stakeholders and decision-makers in the account.

**How:**

#### 4.1 Contact Discovery

Map all known contacts:

```markdown
## Stakeholder Map: [Company Name]

### Current Contacts

| Name | Role | Phone | Email | Relationship | Influence |
|------|------|-------|-------|--------------|-----------|
| John Smith | Purchasing Manager | 07XXX | john@abc.com | Strong (8 years) | High |
| Sarah Jones | Accounts Payable | 01onal | sarah@abc.com | Moderate | Low |
| Mike Brown | MD | Unknown | Unknown | None | Very High |

### Relationship Strength (1-5):
- John Smith: 4/5 (Regular calls, first-name basis)
- Sarah Jones: 2/5 (Invoice queries only)

### Influence Levels:
- **Very High:** Makes final decisions
- **High:** Recommends and influences
- **Medium:** Inputs to decisions
- **Low:** Administrative only
```

#### 4.2 Identify Missing Contacts

For B2B penetration, you need relationships with:

```markdown
### Required Stakeholder Coverage

| Role | Have Contact? | Name | Priority to Obtain |
|------|--------------|------|-------------------|
| Owner/MD | ❌ | - | High |
| Purchasing Manager | ✅ | John Smith | - |
| Finance/Accounts | ✅ | Sarah Jones | - |
| Operations Manager | ❌ | - | Medium |
| Site Supervisor(s) | ❌ | - | High |
| End Users | ❌ | - | Medium |

### Multi-Site Accounts
| Site | Contact | Address | Ordering? |
|------|---------|---------|-----------|
| Head Office | John Smith | 123 Main St | ✅ Yes |
| Warehouse | Unknown | Unknown | ❌ No |
| Site 2 | Unknown | Unknown | ❌ No |
```

#### 4.3 Contact Acquisition Strategy

For each missing contact:

```markdown
### Contact Acquisition Plan

**Target: Site Supervisor**
- Ask John Smith for introduction
- Call main line and request department
- Connect on LinkedIn
- Visit site during delivery

**Target: MD/Owner**
- Request meeting through John
- Invite to customer appreciation event
- Send direct mail (annual review offer)
- Follow on LinkedIn with personalized note
```

#### 4.4 Engagement History

Track all interactions:

```markdown
### Recent Engagement Log

| Date | Contact | Type | Topic | Follow-up |
|------|---------|------|-------|-----------|
| 15 Jan | John Smith | Call | Quarterly check-in | Sample pack sent |
| 22 Jan | John Smith | Email | New product launch | Awaiting response |
| 28 Jan | Sarah Jones | Email | Invoice query | Resolved |
| 03 Feb | John Smith | Call | Sample feedback | Ready to quote |
```

**Tools:** CRM, LinkedIn, Email history, Calendar

**Output:** Complete relationship map with engagement plan

---

### Step 5: Competitive Intelligence

**What:** Understand who else serves this account and where you can win.

**How:**

#### 5.1 Direct Inquiry

Ask contacts directly (in relationship context):

```markdown
## Questions to Ask

"We're always looking to improve. Can I ask..."

**Product Gaps:**
- "Are there any products you need that we don't currently supply?"
- "What else do you typically order for your projects?"

**Competitor Intel:**
- "Who else do you work with for [product category]?"
- "What do you like about working with them?"
- "Is there anything you wish was different about your current suppliers?"

**Service Gaps:**
- "How could we make your ordering easier?"
- "What's most important to you - price, speed, or service?"

**Decision Process:**
- "When you're choosing a supplier, what matters most?"
- "Who else is involved in purchasing decisions?"
```

#### 5.2 Indirect Research

Gather intel without asking:

```markdown
### Competitor Evidence

**Products delivered to their site:**
- Seen [Competitor] packaging on site visit
- Noticed [Brand] tools in use

**Online Research:**
- Company LinkedIn shows partnership with [Competitor]
- Website mentions [Supplier] as partner

**Industry Intel:**
- Trade show attendance with [Competitor]
- Listed on [Competitor] customer page
```

#### 5.3 Competitive Analysis

For each identified competitor:

```markdown
### Competitor: Toolstation

**What they likely supply:**
- Power tools
- Consumables (tape, drill bits)
- Emergency/same-day items

**Their strengths:**
- 30+ locations for trade counter
- Same-day availability
- Wide range

**Their weaknesses:**
- Premium pricing
- Limited trade account benefits
- No dedicated account manager

**Our strategy to compete:**
- Match convenience with next-day delivery
- Better pricing on bulk orders
- Personal service advantage
- Stock critical items for them
```

**Tools:** CRM notes, Google, LinkedIn, Site visits

**Output:** Competitive landscape document with win strategies

---

### Step 6: Account Strategy Development

**What:** Create a strategic plan to grow the account over next 12 months.

**How:**

#### 6.1 Set Account Objectives

```markdown
## Account Growth Plan: [Company Name]

### 12-Month Objectives

**Revenue Targets:**
- Current annual revenue: £10,000
- 12-month target: £15,000 (+50%)
- Quarterly targets: Q1 £3,000 → Q2 £3,500 → Q3 £4,000 → Q4 £4,500

**Product Expansion:**
- Current categories purchased: 5
- Target categories: 8 (+3)
- New categories to penetrate: Power Tools, Consumables, Storage

**Relationship Expansion:**
- Current contacts: 2
- Target contacts: 5 (+3)
- Key contacts to add: MD, Site Supervisor, Secondary Purchaser
```

#### 6.2 Strategic Initiatives

Define 3-5 initiatives to achieve objectives:

```markdown
### Initiative 1: Cable Ties Range Expansion
**Goal:** Increase cable tie revenue from £4,200 to £6,000
**Actions:**
- Send sample pack of 6 variants not currently purchased
- Quote volume discounts for larger orders
- Suggest auto-replenishment program
**Timeline:** Month 1-3
**Owner:** Account Manager

### Initiative 2: Tool Category Entry
**Goal:** Win £2,000 in new tool business
**Actions:**
- Arrange tool demonstration day on-site
- Provide tool trial program (2-week loan)
- Offer first order 20% discount
**Timeline:** Month 2-4
**Owner:** Account Manager + Product Specialist

### Initiative 3: Multi-Site Expansion
**Goal:** Expand ordering to 2 additional sites
**Actions:**
- Map all company sites
- Request introduction to site contacts
- Set up satellite account or consolidated billing
**Timeline:** Month 3-6
**Owner:** Account Manager + Sales Director

### Initiative 4: QBR Program
**Goal:** Establish strategic partnership status
**Actions:**
- Schedule quarterly business review
- Present spend analysis and savings opportunities
- Discuss annual planning together
**Timeline:** Quarterly (Month 3, 6, 9, 12)
**Owner:** Account Manager

### Initiative 5: Preferred Supplier Agreement
**Goal:** Become primary supplier for 3+ categories
**Actions:**
- Propose preferred supplier agreement
- Offer volume-based rebates
- Agree to stock specific items for them
**Timeline:** Month 6-12
**Owner:** Sales Director
```

#### 6.3 Resource Requirements

```markdown
### Resources Needed

**Budget:**
- Samples: £200
- Trade account incentives: £500 (rebates)
- Entertainment/events: £150

**Time:**
- Account Manager: 4 hours/month
- Product Specialist: 2 hours (one-time demo)
- Sales Director: 2 hours (PSA negotiation)

**Materials:**
- Sample packs
- Product catalogs
- Case studies
- Proposal templates
```

**Tools:** CRM, Account planning template, Goal tracking

**Output:** Documented 12-month account strategy

---

### Step 7: Quarterly Business Review (QBR)

**What:** Conduct a structured review meeting to strengthen relationship and identify opportunities.

**How:**

#### 7.1 QBR Preparation (1 week before)

```markdown
## QBR Preparation Checklist

**Data Collection:**
- [ ] Pull 12-month order history
- [ ] Calculate total spend and savings delivered
- [ ] Identify purchasing trends
- [ ] Note any issues/complaints and resolutions
- [ ] Prepare cross-sell recommendations (3-5)

**Content Preparation:**
- [ ] Create presentation deck (template below)
- [ ] Prepare printed report summary
- [ ] Bring product samples/catalogs
- [ ] Prepare pricing for recommended products

**Logistics:**
- [ ] Confirm meeting attendees (request MD attendance)
- [ ] Book meeting room or video call
- [ ] Plan for 45-60 minutes
- [ ] Bring notepad for action items
```

#### 7.2 QBR Agenda Template

```markdown
## Quarterly Business Review Agenda

**Account:** [Company Name]
**Date:** [Date]
**Attendees:** [Names and roles]
**Duration:** 60 minutes

### 1. Relationship Check (5 mins)
- How is business going generally?
- Any changes in your team or operations?
- Any concerns or feedback for us?

### 2. Partnership Review (15 mins)
- Spend summary: Last quarter vs prior quarter
- Top products purchased
- Cost savings delivered
- Service level review (delivery, quality, support)
- Issue resolution summary

### 3. Insights & Opportunities (15 mins)
- Industry trends we're seeing
- New products relevant to their business
- Optimization opportunities (volume discounts, consolidation)
- Comparison to similar customers (anonymized benchmarks)

### 4. Recommendations (15 mins)
- Product recommendation 1: [Detail]
- Product recommendation 2: [Detail]
- Product recommendation 3: [Detail]
- Special offers or programs available

### 5. Forward Planning (10 mins)
- Their upcoming projects/needs
- Our upcoming changes (pricing, products, delivery)
- Actions and next steps
- Date for next QBR
```

#### 7.3 QBR Presentation Template

**Slide 1: Title**
```
GTSE Quarterly Business Review
[Company Name]
[Quarter] [Year]
Prepared by: [Account Manager]
```

**Slide 2: Partnership Summary**
```
YOUR GTSE PARTNERSHIP

Partnership since: [Year]
Account tier: [Gold/Silver/Bronze]
Your dedicated contact: [Name, Phone, Email]

Last 12 months together:
- Total orders: XX
- Total investment: £XX,XXX
- Estimated savings vs RRP: £X,XXX
```

**Slide 3: Quarterly Performance**
```
THIS QUARTER AT A GLANCE

| Metric | Q[X] | vs Last Q | vs Last Year |
|--------|------|-----------|--------------|
| Orders | XX | +XX% | +XX% |
| Value | £X,XXX | +XX% | +XX% |
| Products | XX | +XX% | +XX% |

Top 5 Products This Quarter:
1. Product A - £XXX
2. Product B - £XXX
3. ...
```

**Slide 4: Service Performance**
```
HOW WE'VE SERVED YOU

✅ Delivery performance: XX% on-time
✅ Order accuracy: XX%
✅ Returns processed: X (resolved within X days avg)
✅ Query response time: X hours average

Any issues? Here's what we did:
- [Issue] → [Resolution]
```

**Slide 5: Market Insights**
```
INDUSTRY INSIGHTS

📈 What we're seeing in [their industry]:
- [Trend 1 - e.g., "Shift to UV-resistant materials"]
- [Trend 2 - e.g., "Increased demand for larger pack sizes"]

🏢 How similar customers are saving:
- Consolidating orders to reduce deliveries
- Using auto-replenishment programs
- Standardizing on fewer SKUs
```

**Slide 6: Recommendations**
```
OPPORTUNITIES FOR YOU

Based on your purchasing patterns:

1. [Product Category] - Currently buying elsewhere?
   → Our solution: [Product], benefit: [X], offer: [Y]

2. [Volume Opportunity]
   → Increase order size to £500+ for free delivery
   → Estimated annual savings: £XXX

3. [Efficiency Opportunity]
   → Auto-replenishment for [products]
   → Never run out, automatic pricing
```

**Slide 7: Special Offers**
```
EXCLUSIVE THIS QUARTER

🎁 For you specifically:
- 20% off first order in [new category]
- Free sample pack of [new products]
- Volume discount: Extra 5% on orders £1,000+

Valid until: [Date]
```

**Slide 8: Your Upcoming Needs**
```
PLANNING AHEAD

Tell us about:
- Any upcoming projects?
- Busy periods we should prepare for?
- Products you need that we don't supply?
- Any concerns or improvement areas?
```

**Slide 9: Action Items & Next Steps**
```
ACTIONS FROM TODAY

| Action | Owner | Due Date |
|--------|-------|----------|
| [Action 1] | [Name] | [Date] |
| [Action 2] | [Name] | [Date] |

📅 Next QBR: [Date - 3 months out]
```

#### 7.4 Post-QBR Follow-up

Within 48 hours:

```markdown
## Post-QBR Email Template

Subject: QBR Summary & Actions - GTSE x [Company Name]

Hi [Contact],

Thank you for taking the time to meet today. It was great catching up and learning about your plans for [their project/period].

**Summary of Discussion:**
- [Key point 1]
- [Key point 2]
- [Key point 3]

**Agreed Actions:**

| Action | Owner | Due |
|--------|-------|-----|
| Send samples of [product] | GTSE (Me) | [Date] |
| Provide quote for [X] | GTSE (Me) | [Date] |
| Connect us with [person] | [Their name] | [Date] |

**Attachments:**
- QBR Presentation (PDF)
- Special offer details
- Product information for [recommended products]

**Next QBR:** [Date] - I'll send a calendar invite.

If you need anything in the meantime, I'm always available at [phone] or [email].

Best regards,
[Name]
Account Manager, GTSE
```

**Tools:** PowerPoint/Google Slides, CRM, Email

**Output:** Completed QBR with documented actions

---

### Step 8: Expansion Execution

**What:** Execute the growth initiatives identified in strategy phase.

**How:**

#### 8.1 New Category Introduction

**Process for introducing products they don't currently buy:**

```markdown
## Category Introduction Process

### Step 1: Product Selection
Choose 3-5 products from target category most likely to succeed:
- Match their industry/use case
- Competitive pricing
- High quality/good reviews
- Available in stock

### Step 2: Sample Program
- Send sample pack (no obligation)
- Include product data sheets
- Add personal note explaining recommendation
- Follow up in 1 week

### Step 3: Trial Offer
"Try before you commit" options:
- First order discount (15-20%)
- Money-back guarantee
- Small quantity trial pack
- Tool loan program (return or buy)

### Step 4: Proof Points
- Provide case study from similar customer
- Share testimonials
- Offer reference calls
- Demonstrate ROI calculation

### Step 5: Conversion
- Quote based on their estimated volume
- Include in regular order prompt
- Add to their "favorites" in system
- Train their team on product usage
```

#### 8.2 Multi-Site Expansion

**Process for expanding to additional locations:**

```markdown
## Multi-Site Expansion Process

### Step 1: Site Discovery
Get complete list of all company sites:
- Ask primary contact
- Check Companies House for branches
- Research online (Google Maps, LinkedIn)
- Review delivery addresses in order history

### Step 2: Contact Mapping
For each site, identify:
- Site manager/supervisor
- Person who orders supplies
- Decision maker for that site

### Step 3: Introduction Request
Ask primary contact:
"We'd love to support your other sites too. Would you be able to introduce me to [Site Manager] at [Location]?"

### Step 4: Site-Specific Setup
Options to offer:
- Same account, multiple delivery addresses
- Separate sub-accounts rolling up
- Consolidated monthly invoicing
- Site-specific stock holding

### Step 5: Pilot Program
- Start with one product category
- Prove service level
- Expand product range
- Replicate to additional sites
```

#### 8.3 Volume Growth Programs

**Programs to increase order size and frequency:**

```markdown
## Volume Growth Programs

### Auto-Replenishment
- Customer agrees to regular delivery schedule
- We hold stock for them
- Preferential pricing locked in
- Reduces their admin burden

**Pitch:** "Based on your cable tie usage, we could set up automatic monthly delivery of X units. You'd get 5% better pricing, guaranteed availability, and one less thing to think about. Interested?"

### Bulk Order Incentives
| Order Value | Discount |
|-------------|----------|
| £250-499 | 3% |
| £500-999 | 5% |
| £1,000-2,499 | 8% |
| £2,500+ | 10% |

### Annual Agreement
- Commit to annual volume target
- Receive retrospective rebate
- Price protection for 12 months
- Priority service level

**Example:**
"If you commit to £12,000 spend this year (£3,000/quarter), we'll provide 5% retrospective rebate (£600 back) plus lock in current pricing."

### Early Payment Incentive
- 2% discount for payment within 7 days
- Improves cash flow for both parties
- Strengthens relationship
```

#### 8.4 Progress Tracking

Track expansion initiatives:

```markdown
## Initiative Tracking Dashboard

### Initiative: Cable Tie Range Expansion
- Start date: 15 Jan
- Target: +£1,800 revenue
- Status: In Progress

| Milestone | Target Date | Status | Notes |
|-----------|-------------|--------|-------|
| Sample pack sent | 20 Jan | ✅ Complete | 6 variants sent |
| Follow-up call | 27 Jan | ✅ Complete | Positive feedback |
| Quote provided | 30 Jan | ✅ Complete | £1.2k quoted |
| First order | 15 Feb | 🔄 Pending | Awaiting response |
| Second order | 15 Mar | ⏳ | |

Current revenue from initiative: £480
Conversion rate: 27%
```

**Tools:** CRM, Project tracking, Spreadsheet dashboard

**Output:** Active execution of expansion initiatives with progress tracking

---

### Step 9: Account Health Monitoring

**What:** Establish ongoing monitoring to catch issues early and maintain growth.

**How:**

#### 9.1 Alert System

Configure automated alerts:

```markdown
## Account Alert Configuration

### Critical Alerts (Immediate action required)
- No order in 45 days (previously regular customer)
- Order value drops >50% vs average
- Customer complaint escalated
- Credit hold applied

### Warning Alerts (Review within 1 week)
- No order in 30 days
- Order value drops >25%
- Product return requested
- Late payment (7+ days)
- Contact email bounced

### Opportunity Alerts (Review within 2 weeks)
- Order value increases >50%
- New product category ordered
- New contact person ordering
- Requested product not in stock
```

#### 9.2 Regular Review Cadence

```markdown
## Account Review Schedule

### Daily (5 mins)
- Check for any alerts triggered
- Review today's orders from key accounts
- Respond to any customer queries

### Weekly (30 mins)
- Review orders from top 20 accounts
- Check for any declining patterns
- Prepare outreach for at-risk accounts

### Monthly (2 hours)
- Full account health review (all accounts)
- Update health scores
- Review initiative progress
- Plan next month's activities

### Quarterly (4 hours)
- Conduct QBRs with top 10 accounts
- Full account strategy review
- Update 12-month plans
- Report to management
```

#### 9.3 Win-Back Process

For accounts showing decline:

```markdown
## Win-Back Process

### Stage 1: Early Warning (Order gap 30-45 days)
Action: Friendly check-in call/email
Script: "Hi [Name], noticed it's been a few weeks since your last order. Just checking in - is there anything you need? Any issues we should know about?"

### Stage 2: Active Concern (Order gap 45-60 days)
Action: Direct call with value offer
Script: "We've missed you! I wanted to reach out personally. Is everything okay? I'd love to help you with your next order - I can offer [incentive]."

### Stage 3: Critical (Order gap 60+ days)
Action: Manager escalation + special offer
Script: "I've asked our Sales Manager to reach out. We value your business and want to make sure we're meeting your needs. Can we schedule a call to discuss?"

### Stage 4: Recovery Offer
- One-time 20% discount on next order
- Free delivery for 3 months
- Product samples for new lines
- Extended credit terms

### Stage 5: Exit Interview
If customer confirms churn:
- Ask: What made you change suppliers?
- Ask: What could we have done differently?
- Ask: Would you consider us for future needs?
- Document learnings for other accounts
```

**Tools:** CRM alerts, Calendar reminders, Dashboard

**Output:** Active monitoring system with intervention triggers

---

## Examples

### Example 1: ABC Electrical Contractors Ltd

**Account Profile:**
- Annual revenue: £12,500
- Primary contact: John Smith (Purchasing Manager)
- Account age: 6 years
- Tier: Gold

**Health Assessment Results:**
- Health Score: 3.4/5 (Stable)
- Risk: Order frequency declining (8 orders/quarter → 5 orders/quarter)
- Opportunity: Only purchasing 4 of 12 categories we offer

**Purchase Analysis Findings:**
- 65% of spend on Cable Ties (£8,125)
- 20% on Fixings (£2,500)
- 15% on Hand Tools (£1,875)
- Missing: Power Tools, Consumables, PPE, Test Equipment

**Cross-Sell Opportunities Identified:**
1. Cable Tie Gun (£45) - Would improve their productivity
2. Insulation Tape (estimated £400/year) - Currently buying elsewhere
3. Test Equipment - They're an electrical contractor, must use these
4. Safety Glasses (£300/year estimated) - Compliance requirement

**Relationship Gaps:**
- No relationship with MD
- No contact at their second site (Liverpool)
- Only know purchasing, not end users

**Strategy Developed:**
- 12-month revenue target: £18,000 (+44%)
- Key initiatives:
  1. Tape & consumables conversion (£500 target)
  2. Liverpool site expansion (£3,000 target)
  3. Test equipment introduction (£2,000 target)

**QBR Conducted:**
- Met with John Smith + Operations Manager (new contact)
- Presented £1,200 savings delivered last year
- Introduced 3 recommendations
- Agreed action: Site visit to Liverpool branch

**Results After 6 Months:**
- Revenue: £9,200 (tracking to £18,400 annual)
- New category: Consumables (tape, labels) now regular
- Liverpool site: First order £420, ongoing relationship
- New contact: Site supervisor at Liverpool
- Health Score: 4.1/5 (Improved to Healthy)

---

### Example 2: XYZ Facilities Management

**Account Profile:**
- Annual revenue: £4,800
- Primary contact: Sarah Chen (Procurement)
- Account age: 2 years
- Tier: Silver

**Problem Identified:**
- Order gap: 52 days (longest ever)
- Last order 40% smaller than average
- Email response rate dropped

**Investigation:**
- Called Sarah - went to voicemail
- Tried alternative contact - no answer
- Checked LinkedIn - Sarah moved companies
- Researched - New procurement contact identified

**Win-Back Actions:**
1. Identified new contact: Mike Williams
2. LinkedIn connection request (accepted)
3. Introductory call: Explained GTSE relationship, asked about needs
4. Learned: New procurement process being implemented
5. Offered: QBR to restart relationship properly

**QBR with New Contact:**
- Presented history and value delivered
- Learned their new requirements (faster delivery)
- Agreed trial period with expedited shipping
- Provided samples of new products

**Results:**
- Relationship re-established
- Ordering resumed within 2 weeks
- Added to new vendor system
- Revenue recovered to previous level
- New opportunity: Additional FM contracts they manage

---

## Output Format

### Account Penetration Dashboard

```markdown
# Account Penetration Dashboard

## Summary
- Total managed accounts: XX
- Total annual revenue: £XXX,XXX
- Avg health score: X.X/5

## Status by Health
| Status | Count | Revenue | % of Total |
|--------|-------|---------|------------|
| Healthy (4.0+) | XX | £XXX,XXX | XX% |
| Stable (3.0-3.9) | XX | £XX,XXX | XX% |
| At Risk (2.0-2.9) | XX | £XX,XXX | XX% |
| Critical (<2.0) | XX | £X,XXX | XX% |

## This Month's Focus Accounts
| Account | Status | Initiative | Next Action |
|---------|--------|------------|-------------|
| ABC Ltd | Stable | Category expansion | QBR 15th |
| XYZ Co | At Risk | Win-back | Call today |
| 123 Inc | Healthy | Multi-site | Site visit |

## Initiative Progress
| Initiative | Target | Actual | Status |
|------------|--------|--------|--------|
| New category revenue | £50,000 | £32,000 | 🟡 64% |
| Multi-site expansion | 10 sites | 7 sites | 🟡 70% |
| QBRs completed | 20 | 18 | 🟢 90% |
```

### Account Plan Document

```markdown
# Account Plan: [Company Name]

**Last Updated:** [Date]
**Account Manager:** [Name]
**Review Date:** [Next QBR]

## Account Summary
[Key facts about the account]

## Current Health: X.X/5

## 12-Month Objectives
- Revenue target: £XX,XXX
- New categories: X
- New contacts: X

## Active Initiatives
1. [Initiative name] - [Status] - [Progress]
2. [Initiative name] - [Status] - [Progress]

## Recent Engagement
| Date | Type | Summary |
|------|------|---------|
| [Date] | [Call/Email/Visit] | [Notes] |

## Next Actions
- [ ] [Action] - Due [Date]
- [ ] [Action] - Due [Date]

## Risk Factors
- [Any concerns]

## Notes
[Additional context]
```

---

## Related Skills

- [B2B Cold Outreach](../cold-outreach/SKILL) - Acquiring new accounts
- [B2B Outreach Sequencer](../outreach-sequencer/SKILL) - Multi-touch campaigns
- [Pricing Strategy](../../ecommerce/pricing-strategy/SKILL) - Volume pricing
- [Email Automation](../../marketing/email-automation/SKILL) - Automated nurture
- [Demand Forecasting](../../operations/demand-forecasting/SKILL) - Inventory for key accounts

---

## Appendix

### A: Account Health Score Calculator

```
Score = (Recency × 0.25) + (Frequency × 0.20) + (Revenue × 0.20) + 
        (Diversity × 0.15) + (Engagement × 0.10) + (Payment × 0.10)

Where each factor is scored 1-5:

Recency (days since last order):
5 = 0-7 days
4 = 8-14 days
3 = 15-30 days
2 = 31-60 days
1 = 60+ days

Frequency (orders per quarter vs previous):
5 = +20% or more
4 = +5% to +19%
3 = -5% to +4%
2 = -6% to -25%
1 = -26% or worse

Revenue (12-month trend):
5 = +20% or more
4 = +10% to +19%
3 = -10% to +9%
2 = -11% to -30%
1 = -31% or worse

Diversity (product categories purchased):
5 = 6+ categories
4 = 4-5 categories
3 = 2-3 categories
2 = 1 category
1 = Single product only

Engagement (response to outreach):
5 = Proactively reaches out
4 = Responds within 24 hours
3 = Responds within 3 days
2 = Responds eventually
1 = Rarely/never responds

Payment (average days beyond terms):
5 = Always early
4 = Always on time
3 = Occasionally 1-7 days late
2 = Often 7-30 days late
1 = Frequently 30+ days late
```

### B: QBR Template Download

A complete QBR presentation template is available in:
`/templates/qbr/GTSE-QBR-Template.pptx`

### C: Cross-Sell Matrix by Industry

| Industry | Primary Products | Cross-Sell Targets |
|----------|-----------------|-------------------|
| Electrical Contractor | Cable ties, electrical | Tools, test equipment, PPE |
| Plumber | Fixings, sealants | Tools, fittings, safety |
| General Builder | Fixings, screws | Tools, PPE, consumables |
| Facilities Management | Consumables, safety | Maintenance, cleaning |
| Manufacturing | Bulk consumables | Packaging, safety, tools |

### D: Objection Handling

| Objection | Response |
|-----------|----------|
| "We have a supplier for that" | "I understand. Would you be open to comparing? We might be able to offer better value or service." |
| "Your prices are too high" | "Let's look at total cost including delivery, service, and time. Often we're more competitive than it appears." |
| "We're not interested" | "Completely understand. Can I ask what would need to change for you to consider us?" |
| "Call back another time" | "Of course. When specifically would work? And is there anything I can send over in the meantime?" |
| "We're happy with current supplier" | "That's great to hear. Many of our best customers said the same before trying us. Would a small trial be worth exploring?" |

---

*Version 1.0.0 | Last Updated: 2025*
*For GTSE internal use - Confidential*
