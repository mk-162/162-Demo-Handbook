---
name: amazon-product-launch
title: Amazon Product Launch Playbook
description: Complete end-to-end Amazon product launch strategy from research to 90-day optimization
version: 1.0.0
tags: [amazon, product-launch, ppc, listing-optimization, marketplace]
---

# Amazon Product Launch Playbook

## Purpose

This skill provides a comprehensive, step-by-step guide for launching products on Amazon UK and EU marketplaces. It covers everything from initial market research through listing creation, PPC strategy, review generation, and 90-day optimization cycles.

**Use this skill when:**
- Launching a new product on Amazon for the first time
- Expanding existing products to new Amazon marketplaces
- Re-launching underperforming products with a fresh strategy
- Creating a launch timeline for product development teams

**GTSE Context:** This skill is optimized for industrial/trade products like cable ties, fixings, fasteners, and tools where B2B and trade customers dominate the buyer pool.

## Inputs

- `product_name`: The product being launched (e.g., "Heavy Duty Cable Ties 300mm x 4.8mm Black")
- `product_category`: Amazon category (e.g., "DIY & Tools > Electrical > Cable Management")
- `target_price`: Intended selling price including VAT
- `cost_price`: Landed cost per unit including shipping and duties
- `initial_stock`: Number of units available for launch
- `launch_date`: Target go-live date
- `competitor_asins`: List of 3-5 competitor ASINs to analyze
- `unique_selling_points`: 3-5 key differentiators

## Prerequisites

Before starting this skill, ensure you have:

1. **Amazon Seller Central Account** - Professional seller account (£25/month) with:
   - Brand Registry enrollment (if you have a trademark)
   - Payment and tax information configured
   - Shipping settings established
   
2. **Product Ready for Sale**
   - Product fully manufactured and QC passed
   - Barcodes (EAN/UPC) purchased and assigned
   - Packaging includes all required compliance information
   
3. **Content Assets Prepared**
   - High-resolution product images (see Step 7)
   - Product specifications and technical data
   - Safety/compliance documentation

4. **Budget Allocated**
   - PPC launch budget: Minimum £500-1000 for first 30 days
   - Promotional budget: 10-20% of revenue for discounts
   - Photography budget if images not yet created

5. **Tools Access**
   - Helium 10 or Jungle Scout subscription (keyword research)
   - Amazon Seller Central access
   - Spreadsheet for tracking metrics

---

## Procedure

### Step 1: Market Research & Validation

**What:** Validate market opportunity and understand competitive landscape before investing in launch.

**How:**

#### 1.1 Search Volume Analysis

Use Helium 10 Cerebro or Jungle Scout Keyword Scout to analyze search volume:

```
Primary Keywords to Research:
1. [Product type] → "cable ties"
2. [Product type + material] → "nylon cable ties"  
3. [Product type + size] → "cable ties 300mm"
4. [Product type + application] → "heavy duty cable ties"
5. [Product type + color] → "black cable ties"
```

**Record for each keyword:**
| Keyword | Monthly Search Volume | Keyword Difficulty | Top 10 Avg Reviews | Top 10 Avg Price |
|---------|----------------------|-------------------|-------------------|------------------|
| cable ties | 45,000 | 78 | 2,340 | £8.99 |
| heavy duty cable ties | 8,200 | 65 | 890 | £12.99 |

**Minimum viable search volume:** 
- Primary keyword: >5,000 monthly searches
- Long-tail variations: >1,000 monthly searches combined

#### 1.2 Competitor Analysis Deep Dive

For each of 5 competitor ASINs, document:

```markdown
## Competitor Analysis: [ASIN]

### Basic Info
- **Brand:** 
- **Title:** 
- **Price:** £X.XX
- **Rating:** X.X stars
- **Review Count:** 
- **BSR (Best Seller Rank):** #XXX in [Category]

### Listing Quality Score (1-10)
- Title optimization: /10
- Bullet points: /10
- Images: /10
- A+ Content: /10
- Backend keywords: /10

### Review Analysis
**5-star highlights (what customers love):**
- 
- 
- 

**1-3 star complaints (opportunities for us):**
- 
- 
- 

### Pricing Intelligence
- Was: £X.XX (strikethrough price)
- Current: £X.XX
- Subscribe & Save: £X.XX (X% discount)
- Lightning deal frequency: 
```

#### 1.3 Calculate Market Entry Viability

**Revenue Potential Formula:**
```
Monthly Revenue = Search Volume × Click-Through Rate × Conversion Rate × Price
```

Example for cable ties:
```
45,000 searches × 5% CTR × 15% CVR × £8.99 = £30,341/month potential
```

**Competitive Gap Score:**
Score each factor 1-5 (5 = major opportunity):
- Price gap (can we offer better value?): /5
- Quality gap (can we improve product?): /5
- Listing gap (can we present better?): /5
- Review gap (is leader vulnerable?): /5
- Brand gap (is category brand-agnostic?): /5

**Proceed if:** Total score ≥ 15/25

**Tools:** Helium 10, Jungle Scout, Amazon search

**Output:** Completed market research document with go/no-go decision

---

### Step 2: Keyword Research & Strategy

**What:** Build comprehensive keyword list for listing optimization and PPC campaigns.

**How:**

#### 2.1 Seed Keyword Expansion

Start with 5-10 seed keywords and expand using:

**Helium 10 Magnet:**
1. Enter seed keyword
2. Filter by search volume >100
3. Export top 200 keywords
4. Remove irrelevant terms

**Amazon Search Suggestions:**
1. Type seed keyword in Amazon search
2. Note autocomplete suggestions
3. Add letters A-Z after keyword for more suggestions
4. Example: "cable ties a..." → "cable ties assorted", "cable ties adhesive"

**Competitor Keyword Mining (Cerebro):**
1. Enter top 5 competitor ASINs
2. Export keywords they rank for
3. Filter: Search volume >500, Position <50
4. Identify keywords we can win

#### 2.2 Keyword Categorization

Organize keywords into tiers:

**Tier 1 - Primary Keywords (Use in Title)**
Highest volume, most relevant:
```
cable ties - 45,000
zip ties - 22,000  
cable tie - 18,000
nylon cable ties - 12,000
```

**Tier 2 - Secondary Keywords (Use in Bullets/Description)**
Medium volume, relevant variations:
```
heavy duty cable ties - 8,200
black cable ties - 6,500
cable ties 300mm - 4,100
cable ties bulk - 3,800
cable management - 3,200
```

**Tier 3 - Long-tail Keywords (Use in Backend)**
Lower volume but high intent:
```
cable ties for outdoor use - 890
uv resistant cable ties - 720
releasable cable ties - 680
cable ties for car - 540
```

**Tier 4 - Application Keywords (Use in A+ Content)**
Problem/solution focused:
```
organize cables - 2,100
cable tidy - 1,900
wire management - 1,400
garden ties - 1,200
```

#### 2.3 Create Keyword Master Document

```
| Keyword | Search Vol | Tier | Use Location | PPC Bid |
|---------|------------|------|--------------|---------|
| cable ties | 45,000 | 1 | Title | £0.85 |
| zip ties | 22,000 | 1 | Title | £0.72 |
| nylon cable ties | 12,000 | 1 | Title | £0.65 |
| heavy duty cable ties | 8,200 | 2 | Bullet 1 | £0.58 |
```

**Tools:** Helium 10 Cerebro, Helium 10 Magnet, Amazon Autocomplete

**Output:** Keyword master spreadsheet with 100-200 organized keywords

---

### Step 3: Listing Creation - Title

**What:** Create a keyword-rich, readable title that maximizes visibility and click-through rate.

**How:**

#### 3.1 Amazon Title Formula

**Structure (200 characters max, 80 characters ideal for mobile):**
```
[Brand] + [Primary Keyword] + [Key Feature 1] + [Key Feature 2] + [Size/Quantity] + [Secondary Keyword]
```

**Character priority:**
- First 80 characters: Most critical (mobile display)
- Characters 81-150: Desktop visibility
- Characters 151-200: Backend indexing only

#### 3.2 GTSE Title Examples

**Cable Ties Example:**
```
GTSE Heavy Duty Cable Ties 300mm x 4.8mm Black, Pack of 100 - Professional Grade Nylon Zip Ties, UV Resistant for Indoor Outdoor Use
```
(147 characters)

**Breakdown:**
- Brand: GTSE
- Primary keyword: Heavy Duty Cable Ties
- Specifications: 300mm x 4.8mm Black
- Quantity: Pack of 100
- Key feature: Professional Grade Nylon Zip Ties
- Benefit: UV Resistant for Indoor Outdoor Use

**Screws/Fixings Example:**
```
GTSE Wood Screws 4 x 40mm, Box of 200 - Yellow Zinc Plated Pozi Countersunk Screws, Self-Tapping for Hardwood Softwood
```

**Tool Kit Example:**
```
GTSE Professional Electrician Tool Set, 18-Piece - Insulated VDE Screwdrivers, Wire Strippers & Cable Cutters in Carry Case
```

#### 3.3 Title Checklist

✅ **Do Include:**
- [ ] Brand name at start
- [ ] Primary keyword in first 80 characters
- [ ] Size/dimensions/quantity
- [ ] Material if relevant
- [ ] 1-2 key benefits
- [ ] Color if variant-specific

❌ **Don't Include:**
- [ ] Price or promotional info
- [ ] Shipping information
- [ ] Excessive punctuation (!!!)
- [ ] ALL CAPS sections
- [ ] Competitor brand names
- [ ] Unverified claims (best, #1)

**Tools:** Amazon Seller Central, Character counter

**Output:** Optimized 150-200 character title

---

### Step 4: Listing Creation - Bullet Points

**What:** Create 5 compelling bullet points that convert browsers to buyers.

**How:**

#### 4.1 Bullet Point Framework

Each bullet should follow: **FEATURE + BENEFIT + PROOF**

```
[EMOJI] [FEATURE IN CAPS] - [Benefit to customer] [Proof/specification]
```

**Character limits:**
- Maximum: 500 characters per bullet
- Recommended: 200-250 characters per bullet
- Total: 1,000-1,250 characters across all 5

#### 4.2 The 5-Bullet Formula

**Bullet 1: Primary Feature/USP**
The main reason someone should buy this product.

**Bullet 2: Quality/Materials**
What it's made of and why that matters.

**Bullet 3: Practical Application**
How and where to use it.

**Bullet 4: Specifications/Contents**
Technical details buyers need.

**Bullet 5: Guarantee/Trust Signal**
Risk reversal and brand credibility.

#### 4.3 GTSE Bullet Examples - Cable Ties 300mm

```
🔧 PROFESSIONAL GRADE STRENGTH - These heavy-duty cable ties feature a tensile strength of 22kg (50lbs), ensuring your cables, wires, and equipment stay securely fastened. Trusted by electricians, installers, and tradespeople across the UK.

📦 PACK OF 100 - GREAT VALUE - Each pack contains 100 premium black nylon cable ties measuring 300mm x 4.8mm (12" x 0.19"). Perfect for bulk electrical work, cable management projects, or keeping as workshop essentials.

☀️ UV RESISTANT FOR INDOOR & OUTDOOR USE - Made from PA66 nylon with UV stabilizers, these zip ties won't crack or degrade in sunlight. Ideal for outdoor installations, garden use, securing fence panels, or any exterior cable management.

📏 PRECISE DIMENSIONS FOR VERSATILE USE - 300mm length accommodates cable bundles up to 80mm diameter. Self-locking mechanism with smooth head prevents cable damage. Temperature range: -40°C to +85°C for any British weather.

✅ GTSE QUALITY GUARANTEE - Family-run UK business with 10+ years experience supplying trade customers. Full technical support available. Not satisfied? Contact us for hassle-free replacement or refund.
```

#### 4.4 Bullet Point Checklist

✅ **Each bullet should:**
- [ ] Start with relevant emoji (optional but recommended)
- [ ] Lead with capitalized feature header
- [ ] Include a customer benefit
- [ ] Contain at least one keyword
- [ ] Be scannable (not wall of text)
- [ ] Address a customer question or concern

❌ **Avoid:**
- [ ] Repeating the same information
- [ ] Promotional language (sale, discount, limited time)
- [ ] HTML or formatting codes
- [ ] Competitor comparisons
- [ ] Unsubstantiated superlatives

**Tools:** Amazon Seller Central, Keyword reference document

**Output:** 5 optimized bullet points totaling 1,000-1,250 characters

---

### Step 5: Listing Creation - Product Description

**What:** Create a detailed product description for enhanced discoverability (note: A+ Content replaces this visually but description still indexes for search).

**How:**

#### 5.1 Description Structure (2,000 characters max)

```
[Opening Hook - Problem/Solution]

[Detailed Product Information]

[Technical Specifications]

[Use Cases/Applications]

[Brand Story/Trust Elements]

[Call to Action]
```

#### 5.2 GTSE Description Example - Cable Ties

```
PROFESSIONAL CABLE MANAGEMENT MADE EASY

Tired of messy cables and unreliable zip ties that snap under pressure? GTSE Heavy Duty Cable Ties are engineered for professionals who demand reliability on every job.

WHAT MAKES GTSE CABLE TIES DIFFERENT?

Our 300mm x 4.8mm black cable ties are manufactured from premium PA66 nylon, the same material trusted in automotive and aerospace applications. With a tensile strength of 22kg, these ties won't fail when you need them most.

PERFECT FOR:
• Electrical installations and cable management
• Data centre and server room organization  
• Outdoor applications (UV resistant)
• Automotive wiring and hose bundling
• Garden and landscaping projects
• General warehouse and industrial use

TECHNICAL SPECIFICATIONS:
- Length: 300mm (12 inches)
- Width: 4.8mm (0.19 inches)
- Material: PA66 Nylon
- Colour: Black (UV stabilized)
- Tensile Strength: 22kg (50 lbs)
- Operating Temperature: -40°C to +85°C
- Bundle Diameter: Up to 80mm

TRUSTED BY UK TRADESPEOPLE

GTSE has been supplying the UK trade since 2012. We understand that professionals need products that work first time, every time. Every batch is quality tested before dispatch from our UK warehouse.

COMPLETE SATISFACTION GUARANTEED

Not 100% happy? Contact our UK-based customer service team for a no-quibble replacement or refund. We stand behind every product we sell.

Order your GTSE Heavy Duty Cable Ties today and experience professional-grade quality at trade prices.
```

**Tools:** Amazon Seller Central, Character counter

**Output:** 1,500-2,000 character product description

---

### Step 6: Listing Creation - Backend Keywords

**What:** Add hidden keywords that improve discoverability without cluttering visible content.

**How:**

#### 6.1 Backend Search Terms Rules

**Amazon allows 249 bytes in Search Terms field (approximately 249 characters with standard ASCII)**

**Rules:**
- No commas needed between words
- No repeat words from title
- No brand names (yours or competitors)
- No ASINs
- No subjective claims (best, amazing)
- No temporary statements (new, on sale)

#### 6.2 Backend Keyword Strategy

**Step 1:** Extract keywords NOT already in title
**Step 2:** Prioritize by search volume
**Step 3:** Include misspellings (kabul ties, cabletie)
**Step 4:** Include synonyms (wire ties, band ties, fastener straps)
**Step 5:** Include related terms (cable organizer, cord management)

#### 6.3 GTSE Backend Keywords Example - Cable Ties

```
zip tie wire ties band strap wire tidies cord organiser cable fastener nylon straps reusable ties electrical ties auto ties garden ties fencing ties outdoor ties weatherproof ties tradesman supplies electrician tools plumber supplies contractor accessories self locking ties kabul ties cabletie
```
(247 characters)

#### 6.4 Other Backend Fields

**Subject Matter (5 entries allowed):**
```
1. Cable Management
2. Electrical Supplies  
3. Cable Ties Zip Ties
4. Industrial Fasteners
5. Wire Organisation
```

**Target Audience:**
```
Electricians
Tradespeople
DIY Enthusiasts
Industrial Maintenance
Data Centre Technicians
```

**Tools:** Amazon Seller Central > Edit Listing > Keywords tab

**Output:** Complete backend keyword fields

---

### Step 7: Product Images

**What:** Create 7-9 images that showcase product and drive conversions.

**How:**

#### 7.1 Image Requirements (Amazon Technical Standards)

| Spec | Requirement |
|------|-------------|
| Minimum size | 1000 x 1000 pixels |
| Recommended size | 2000 x 2000 pixels |
| Maximum size | 10,000 x 10,000 pixels |
| Format | JPEG (.jpg) or PNG |
| Color mode | sRGB or CMYK |
| File size | < 10MB |
| Background (main image) | Pure white (RGB 255,255,255) |

#### 7.2 The 9-Image Strategy

**Image 1: Main Image (HERO)**
- Product only on pure white background
- Product fills 85%+ of frame
- No text, graphics, or watermarks
- Show product at realistic scale
- Primary variant visible

**Image 2: Scale/Size Reference**
- Product held in hand OR
- Product next to common object (ruler, coin) OR
- Dimensional callouts showing measurements

**Image 3: Package Contents / What's Included**
- Everything customer receives laid out
- Count clearly visible (e.g., "100 pieces")
- Any included accessories or documentation

**Image 4: Infographic - Key Features**
- 4-6 callouts highlighting main features
- Clean design with icons
- Benefits-focused copy
- GTSE brand colors

**Image 5: Infographic - Specifications**
- Technical specifications
- Dimensions diagram
- Material information
- Compliance marks

**Image 6: Lifestyle/In-Use Shot 1**
- Product being used in realistic setting
- Target customer visible if possible
- Shows primary use case
- Professional quality

**Image 7: Lifestyle/In-Use Shot 2**
- Secondary use case
- Different application or environment
- Demonstrates versatility

**Image 8: Quality/Close-up**
- Macro shot showing material quality
- Texture and build quality visible
- Manufacturing precision

**Image 9: Brand Story / Trust**
- UK business badge
- Guarantee information
- "Family-run since 2012"
- Quality certifications

#### 7.3 GTSE Cable Ties Image Brief

```markdown
## Image 1: Main Product Shot
- Single cable tie pack on white background
- Pack angled 15 degrees for dimension
- Label clearly readable
- Some ties visible through packaging

## Image 2: Size Reference
- Single cable tie held between thumb and forefinger
- Ruler visible showing 300mm length
- Width callout showing 4.8mm

## Image 3: Package Contents
- All 100 cable ties laid out in organized rows
- Pack of 10 x 10 grid formation
- "100 Pack" text overlay

## Image 4: Features Infographic
- Central product image
- Callouts:
  - "22kg Tensile Strength"
  - "PA66 Nylon"
  - "UV Resistant"
  - "Self-Locking Head"
  - "Temperature: -40°C to +85°C"

## Image 5: Specifications Diagram  
- Technical drawing with dimensions
- 300mm length marked
- 4.8mm width marked
- Bundle capacity (80mm diameter)
- Head design close-up

## Image 6: Electrician Using Product
- Electrician in high-vis securing cables in consumer unit
- Professional setting
- Product clearly visible in use

## Image 7: Outdoor Application
- Cable ties securing solar panel cables
- Outdoor setting showing UV resistance claim
- Or: Garden application on trellis/fence

## Image 8: Quality Close-up
- Macro shot of locking mechanism
- Shows precision manufacturing
- Smooth finish on strap

## Image 9: Brand Trust
- GTSE logo
- "UK Family Business Est. 2012"
- "100% Satisfaction Guaranteed"
- Union Jack subtle design element
```

#### 7.4 Image Checklist

✅ **Before uploading, verify:**
- [ ] Main image is pure white background
- [ ] All images are 2000 x 2000 pixels
- [ ] No pixelation or blur
- [ ] Text is readable at thumbnail size
- [ ] Brand colors are consistent
- [ ] No watermarks or competitor logos
- [ ] Mobile preview checked (images still work at 116x116)

**Tools:** Canva, Photoshop, Professional photographer

**Output:** 7-9 optimized product images

---

### Step 8: A+ Content (Enhanced Brand Content)

**What:** Create rich, branded content that replaces product description with visual modules.

**How:**

#### 8.1 A+ Content Requirements

- **Eligibility:** Brand Registry required
- **Modules:** Choose 5-7 from Amazon's templates
- **Images:** 970 x 600 pixels (full width), 300 x 300 (thumbnails)
- **Text:** Complement images, don't repeat bullet points

#### 8.2 Recommended Module Layout

**Module 1: Brand Hero Banner (Standard Image)**
- 970 x 600 pixel branded header
- Product name and key message
- GTSE branding prominent

**Module 2: Company Story (Standard Company Logo)**
- GTSE logo
- "Family-run UK business since 2012"
- Brief mission statement

**Module 3: Key Features (Standard Three Image & Text)**
- Three 300x300 images
- Feature headlines and short descriptions
- Icons representing quality, strength, versatility

**Module 4: Product Specifications (Standard Text)**
- Technical specifications table
- Easy-to-scan format
- Dimensions, materials, ratings

**Module 5: Use Cases (Standard Four Image & Text)**
- Four application images (300x300)
- Brief description of each use
- Electrical, garden, automotive, industrial

**Module 6: Comparison Chart (Standard Comparison)**
- Compare your product variants
- OR compare features vs typical products
- Highlight your advantages

**Module 7: Trust/CTA Banner (Standard Image)**
- Satisfaction guarantee message
- "Add to basket" encouragement
- Final brand reinforcement

#### 8.3 A+ Content Copy Example - Cable Ties

**Module 1 Banner Text:**
```
GTSE HEAVY DUTY CABLE TIES
Professional-Grade Cable Management Trusted by UK Tradespeople
```

**Module 2 Company Story:**
```
ABOUT GTSE

We're a family-run UK business that's been supplying trade customers since 2012. We believe professionals deserve professional-grade tools - reliable products at fair prices with service you can count on.

Every GTSE product is designed with input from the tradespeople who use them daily. From electricians to facilities managers, we listen, learn, and continuously improve.
```

**Module 3 - Three Features:**

*Image 1: Strong arm icon*
```
UNBREAKABLE STRENGTH
22kg tensile strength means these ties won't fail under pressure. Secure heavy cable bundles with confidence.
```

*Image 2: Sun icon*
```
BUILT FOR OUTDOORS  
UV-stabilized PA66 nylon resists sun damage. Perfect for outdoor installations that need to last.
```

*Image 3: Thermometer icon*
```
EXTREME TEMPERATURES
Operating range from -40°C to +85°C. Reliable performance in freezers, server rooms, or rooftops.
```

**Module 5 - Use Cases:**

*Image 1:* Electrical panel
```
ELECTRICAL INSTALLATIONS
Perfect for consumer units, distribution boards, and cable trunking.
```

*Image 2:* Server rack
```
DATA CENTRES
Keep server rooms organized with professional cable management.
```

*Image 3:* Garden/outdoor
```
GARDEN & OUTDOOR
UV resistant for fencing, trellis, and exterior cable routing.
```

*Image 4:* Automotive
```
AUTOMOTIVE
Secure wiring harnesses, hoses, and accessories under the bonnet.
```

**Tools:** Amazon A+ Content Manager, Canva/Photoshop

**Output:** Complete A+ Content submission

---

### Step 9: Pricing Strategy

**What:** Set optimal pricing that maximizes profit while remaining competitive.

**How:**

#### 9.1 Calculate Minimum Viable Price

```
Minimum Price = (Cost Price + Amazon Fees + Shipping) / (1 - Target Margin)
```

**Amazon Fee Structure (UK):**
| Fee Type | Typical Rate |
|----------|--------------|
| Referral Fee | 15% of sale price (most categories) |
| FBA Pick & Pack | £2.14 - £5.00+ (size dependent) |
| Storage (monthly) | £0.75 per cubic foot (standard) |
| Storage (Q4) | £2.40 per cubic foot (Oct-Dec) |

**Example - Cable Ties 100-pack:**
```
Cost Price: £2.50
FBA Pick & Pack: £2.50
Referral Fee (15%): Calculated on sale price
Target Margin: 25%

If selling at £9.99:
- Revenue: £9.99
- Referral Fee: £1.50 (15%)
- FBA Fulfillment: £2.50
- Product Cost: £2.50
- Net Profit: £3.49 (35% margin)
```

#### 9.2 Competitive Pricing Analysis

| Competitor | Price | Pack Size | Per-Unit Price | Rating | Reviews |
|------------|-------|-----------|----------------|--------|---------|
| Comp A | £8.99 | 100 | £0.090 | 4.5 | 2,341 |
| Comp B | £7.49 | 100 | £0.075 | 4.3 | 876 |
| Comp C | £12.99 | 200 | £0.065 | 4.7 | 3,102 |
| **GTSE** | £9.49 | 100 | £0.095 | - | 0 |

#### 9.3 Launch Pricing Strategy

**Phase 1: Launch (Days 1-14)**
- Price: 15-20% below target to drive initial sales
- Goal: Generate velocity and reviews
- Example: £7.99 (Target: £9.49)

**Phase 2: Establishment (Days 15-45)**
- Price: 10% below target
- Maintain momentum while improving margin
- Example: £8.49

**Phase 3: Optimization (Day 46+)**
- Price: Full target price
- Focus on profitability
- Example: £9.49

#### 9.4 Price Tracking Setup

Create price monitoring for:
- [ ] All 5 primary competitors
- [ ] Alert if competitor drops >10%
- [ ] Weekly price review scheduled
- [ ] Promotion calendar mapped

**Tools:** Amazon Revenue Calculator, Keepa, RepricerExpress

**Output:** Pricing strategy document with phase timeline

---

### Step 10: PPC Launch Campaign Structure

**What:** Set up Amazon PPC campaigns to drive traffic and accelerate ranking.

**How:**

#### 10.1 Campaign Architecture

```
Account
├── SP (Sponsored Products)
│   ├── Auto Campaigns (Discovery)
│   │   ├── Auto - [Product] - Close Match
│   │   ├── Auto - [Product] - Loose Match
│   │   ├── Auto - [Product] - Substitutes
│   │   └── Auto - [Product] - Complements
│   │
│   ├── Manual Campaigns (Scaling)
│   │   ├── Manual - [Product] - Exact
│   │   ├── Manual - [Product] - Phrase
│   │   └── Manual - [Product] - Broad
│   │
│   └── ASIN Targeting
│       └── Manual - [Product] - Product Targeting
│
├── SB (Sponsored Brands)
│   └── Brand - [Product Line] - Top Search
│
└── SD (Sponsored Display)
    └── Display - [Product] - Remarketing
```

#### 10.2 Week 1: Auto Campaign Setup

**Campaign 1: Auto Discovery**
- Campaign name: `SP-Auto-CableTies300mm-Discovery`
- Budget: £20/day
- Bidding: Dynamic bids - down only
- All four targeting groups enabled

**Settings:**
| Targeting Group | Bid | Purpose |
|-----------------|-----|---------|
| Close Match | £0.75 | Relevant keyword discovery |
| Loose Match | £0.50 | Related terms |
| Substitutes | £0.60 | Competitor products |
| Complements | £0.40 | Cross-sell opportunities |

**Negative Keywords (Add Immediately):**
- Competitor brand names
- Irrelevant sizes/colors
- Products you don't sell

#### 10.3 Week 2: Manual Campaign Setup

After 7 days of auto data, create manual campaigns:

**Campaign 2: Exact Match**
- Name: `SP-Manual-CableTies300mm-Exact`
- Budget: £30/day
- Match type: Exact only
- Keywords: Top 20 performers from auto

**Campaign 3: Phrase Match**
- Name: `SP-Manual-CableTies300mm-Phrase`
- Budget: £15/day
- Match type: Phrase only
- Keywords: Top 30 from research

**Campaign 4: Broad Match (Modified)**
- Name: `SP-Manual-CableTies300mm-Broad`
- Budget: £10/day
- Match type: Broad
- Keywords: High-volume terms for discovery

#### 10.4 Bid Management Strategy

**Initial Bids:**
| Keyword Tier | Initial Bid | Adjust After |
|--------------|-------------|--------------|
| Tier 1 (primary) | £0.85 | 100 impressions |
| Tier 2 (secondary) | £0.60 | 100 impressions |
| Tier 3 (long-tail) | £0.40 | 100 impressions |

**Optimization Rules:**
```
IF ACoS < 20% AND Sales > 5 → Increase bid 10%
IF ACoS 20-35% → Maintain bid
IF ACoS 35-50% → Decrease bid 10%
IF ACoS > 50% AND Spend > £10 → Decrease bid 20%
IF Zero sales after £15 spend → Pause keyword
```

#### 10.5 Daily PPC Checklist (First 30 Days)

Morning (15 minutes):
- [ ] Check yesterday's spend (any budget cap hits?)
- [ ] Review ACoS by campaign
- [ ] Check for high-spend, no-sale keywords
- [ ] Add any obvious negative keywords

Weekly (30 minutes):
- [ ] Harvest converting search terms from auto
- [ ] Move to manual campaigns as exact match
- [ ] Negate poor performers in auto
- [ ] Adjust bids based on ACoS targets
- [ ] Review placement performance

**Tools:** Amazon Advertising Console, Helium 10 Adtomic, Spreadsheet tracker

**Output:** Complete PPC campaign structure with initial keywords and bids

---

### Step 11: Review Generation Strategy

**What:** Ethically generate early reviews to build social proof.

**How:**

#### 11.1 Amazon Vine Program

**Eligibility:**
- Brand registered products
- Fewer than 30 reviews
- FBA inventory available

**Process:**
1. Seller Central → Advertising → Vine
2. Select ASIN
3. Enroll up to 30 units
4. Pay enrollment fee (£0 for first ASIN)
5. Vine reviewers request products
6. Reviews appear within 2-4 weeks

**Best Practices:**
- Ensure product is 100% ready (no quality issues)
- Have sufficient stock (30+ units)
- Expect honest reviews (4.0 average typical)

#### 11.2 Request a Review Button

**Process:**
1. Seller Central → Orders → Manage Orders
2. Click order → Request a Review
3. Amazon sends templated email to buyer

**Timing Optimization:**
| Product Type | Best Request Timing |
|--------------|---------------------|
| Consumables | 7 days post-delivery |
| Tools/Equipment | 14 days post-delivery |
| Complex products | 21 days post-delivery |

**Automation:**
- Use Helium 10 Follow-Up or similar
- Trigger automatic requests after X days
- Stay within Amazon's one-request limit

#### 11.3 Insert Cards (Amazon Compliant)

**Allowed:**
- Thank you message
- Product tips/instructions
- Customer support contact
- QR code to support page

**NOT Allowed:**
- Review requests
- Incentives for reviews
- Directing to external websites
- Discounts for reviews

**GTSE Insert Card Example:**
```
-----------------------------------------
| THANK YOU FOR YOUR PURCHASE!          |
|                                       |
| Need help? We're here for you.        |
|                                       |
| Scan for product guides & support:    |
| [QR CODE to gtse.co.uk/support]       |
|                                       |
| UK-based team ready to help           |
| support@gtse.co.uk                    |
-----------------------------------------
```

#### 11.4 Review Monitoring

Track weekly:
| Metric | Week 1 | Week 2 | Week 3 | Week 4 |
|--------|--------|--------|--------|--------|
| Total Reviews | 0 | 2 | 5 | 8 |
| Average Rating | - | 4.5 | 4.4 | 4.5 |
| Review Rate | - | 3% | 4% | 5% |

**Review Rate Target:** 2-5% of orders

**Tools:** Amazon Vine, Seller Central, Helium 10 Follow-Up

**Output:** Active review generation program

---

### Step 12: 30-Day Launch Optimization

**What:** Execute daily and weekly optimization tasks during critical launch period.

**How:**

#### 12.1 Daily Tasks (15-20 minutes)

**Sales & Traffic:**
- [ ] Check units sold yesterday
- [ ] Review sessions and conversion rate
- [ ] Note any anomalies

**PPC:**
- [ ] Review spend vs budget
- [ ] Check ACoS trend
- [ ] Quick negative keyword additions

**Inventory:**
- [ ] Verify stock levels
- [ ] Check for stranded inventory alerts

#### 12.2 Weekly Tasks (1-2 hours)

**Week 1:**
- [ ] Verify listing is live and indexed correctly
- [ ] Confirm all images uploaded properly
- [ ] Test search for primary keywords (do we appear?)
- [ ] Monitor initial PPC performance
- [ ] Start Request a Review process

**Week 2:**
- [ ] Harvest converting search terms from auto campaigns
- [ ] Create manual exact match campaigns
- [ ] Review search term report for negatives
- [ ] Check BSR trend
- [ ] First pricing evaluation

**Week 3:**
- [ ] Full PPC audit (ACoS by keyword)
- [ ] Increase bids on winners, decrease on losers
- [ ] Evaluate Vine review submissions
- [ ] A/B test main image if CTR low
- [ ] Consider promotional deals

**Week 4:**
- [ ] Comprehensive performance review
- [ ] Margin analysis with actual data
- [ ] Keyword ranking check for top 10 terms
- [ ] Prepare 60-day plan adjustments

#### 12.3 Key 30-Day Metrics

| Metric | Target | Action if Below |
|--------|--------|-----------------|
| Sessions | >50/day | Increase PPC spend |
| CTR | >0.4% | Improve main image/title |
| Conversion Rate | >10% | Improve bullets/images/price |
| ACoS | <35% | Optimize keywords and bids |
| Review count | 5+ | Push Vine, increase requests |
| BSR | Top 10,000 | Maintain sales velocity |

**Tools:** Seller Central, Brand Analytics, Helium 10

**Output:** Completed 30-day optimization with documented learnings

---

### Step 13: 60-Day Optimization

**What:** Scale successful elements and address underperformance.

**How:**

#### 13.1 Performance Audit

**Sales Analysis:**
```
Days 1-30 Sales: XXX units (£X,XXX revenue)
Days 31-60 Target: +30% growth
Actual Days 31-60: XXX units (£X,XXX revenue)
Growth: X%
```

**PPC Evolution:**
```
Month 1 ACoS: XX%
Month 2 Target ACoS: 25%
Month 2 Actual: XX%

Top 5 Keywords (by revenue):
1. [keyword] - £XXX revenue, XX% ACoS
2. [keyword] - £XXX revenue, XX% ACoS
3. ...
```

#### 13.2 Optimization Actions

**If Conversion Rate <10%:**
- [ ] A/B test price (5% reduction)
- [ ] A/B test main image
- [ ] Revise bullet points
- [ ] Add video if available
- [ ] Review competitor listings for gaps

**If ACoS >35%:**
- [ ] Pause keywords with ACoS >70%
- [ ] Reduce bids on 40-70% ACoS terms by 15%
- [ ] Increase bids on <20% ACoS terms by 10%
- [ ] Add more negative keywords
- [ ] Consider dayparting (pause overnight)

**If Reviews <10:**
- [ ] Audit customer service responses
- [ ] Check product quality feedback
- [ ] Accelerate Vine if available
- [ ] Improve insert card design
- [ ] Consider early reviewer program alternatives

#### 13.3 Expansion Opportunities

**Add Variations:**
- Different pack sizes (50, 200, 500)
- Different colors
- Bundle options

**Cross-Promotion:**
- Create virtual bundles
- Run sponsored display on complement products
- Use "Frequently bought together" optimization

**Tools:** Amazon A/B Testing, Seller Central Reports

**Output:** 60-day review document with action items

---

### Step 14: 90-Day Optimization & Beyond

**What:** Establish sustainable profitability and long-term growth plan.

**How:**

#### 14.1 Profitability Analysis

**Calculate True Profitability:**
```
Gross Revenue: £10,000
Less Returns/Refunds: -£300 (3%)
Net Revenue: £9,700

Less Costs:
- Product Cost: -£2,500 (25%)
- FBA Fees: -£2,300 (23%)
- Referral Fees: -£1,455 (15%)
- PPC Spend: -£1,500 (15%)
- Promotions: -£200 (2%)

Net Profit: £1,745
Profit Margin: 17.5%
```

**Target by Day 90:** 20%+ net profit margin after all costs

#### 14.2 Organic Ranking Evaluation

Check keyword ranking for top 20 keywords:

| Keyword | Day 1 | Day 30 | Day 60 | Day 90 | Target |
|---------|-------|--------|--------|--------|--------|
| cable ties | >100 | 45 | 28 | 15 | Top 10 |
| heavy duty cable ties | >100 | 22 | 12 | 8 | Top 5 |

**Strategy if not ranking:**
- Maintain or increase PPC on exact match
- Run Lightning Deal or 7-Day Deal
- External traffic (social, email) to boost sales velocity

#### 14.3 PPC Maturity

By Day 90, campaigns should show:
- **ACoS:** 15-25% (category dependent)
- **TACoS (Total ACoS):** <10%
- **Auto:Manual ratio:** 20:80 (most spend on proven keywords)
- **Profitable keywords:** 80%+ of spend on <30% ACoS terms

**Mature Campaign Maintenance:**
- Weekly: Search term harvesting
- Bi-weekly: Bid adjustments
- Monthly: Campaign structure review
- Quarterly: Full strategy review

#### 14.4 Long-Term Growth Plan

**Months 4-6:**
- Launch additional variations
- Expand to DE, FR, IT, ES marketplaces
- Build Subscribe & Save enrollment
- Develop virtual bundles

**Months 7-12:**
- Pursue Amazon's Choice badge
- Apply for best seller promotions
- Brand store development
- Video content creation

**Year 2:**
- Category expansion
- New product development
- Wholesale/liquidation strategy for slow movers
- International expansion (US, UAE)

**Tools:** Seller Central, Helium 10, Financial tracking spreadsheet

**Output:** 90-day report with 12-month roadmap

---

## Examples

### Complete Launch Example: GTSE Heavy Duty Cable Ties 300mm

**Pre-Launch (Week -4 to -1):**
- Keyword research completed: 150 keywords categorized
- 5 competitors analyzed: Average price £8.99, ratings 4.3-4.7
- Decision: Launch at £7.99, target £9.49
- Images produced: 9 images, 2000x2000 px
- A+ Content designed and submitted

**Week 1:**
- Listing live on Wednesday
- Auto PPC campaign launched: £20/day
- Day 3: First sale (organic)
- Day 5: 12 sales, BSR #18,000
- Day 7: 28 sales total, enrolled in Vine (30 units)

**Week 2:**
- Created manual exact match campaign with top 15 auto keywords
- Raised auto campaign budget to £30/day
- CTR at 0.35%: Changed main image to include pack count
- 45 sales, BSR #8,500

**Week 3:**
- First Vine review: 5 stars
- 67 sales, BSR #5,200
- ACoS at 32% (target 35% ✓)
- Added phrase match campaign

**Week 4:**
- 4 reviews total (4.5 average)
- 89 sales, BSR #3,800
- Increased price to £8.49
- Conversion rate: 14%

**Day 30 Summary:**
- Total sales: 89 units
- Revenue: £712
- PPC spend: £285
- Net profit (before fixed costs): £187
- Reviews: 4 (4.5 star average)
- BSR: #3,800

**Day 60:**
- Total sales: 247 units (cumulative)
- Monthly revenue: £1,400
- ACoS: 24%
- Reviews: 12 (4.4 average)
- BSR: #2,100
- Raised price to £9.49

**Day 90:**
- Monthly sales: 180 units/month sustained
- Revenue: £1,700/month
- ACoS: 18%
- TACoS: 8%
- Reviews: 28 (4.5 average)
- BSR: #1,500
- Net margin: 22%

---

## Output Format

### Launch Tracking Dashboard

```markdown
# [Product Name] Launch Dashboard

## Status: [Week X / Day XX]

### Key Metrics
| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Daily Sales | 5 | 7 | 🟢 |
| BSR | <5,000 | 3,200 | 🟢 |
| Reviews | 15 | 8 | 🟡 |
| ACoS | <30% | 28% | 🟢 |
| Conversion | >12% | 14% | 🟢 |

### This Week's Actions
- [ ] Action 1
- [ ] Action 2
- [ ] Action 3

### Issues & Blockers
- Issue 1: Description, mitigation plan

### Next Week's Focus
- Focus area 1
- Focus area 2
```

---

## Related Skills

- [Amazon PPC Optimizer](../ppc-optimizer/SKILL) - Deep dive on PPC optimization
- [Amazon Listing Audit](../listing-audit/SKILL) - Audit existing listings
- [Amazon Competitor Monitor](../competitor-monitor/SKILL) - Track competitor changes
- [Amazon Review Response](../review-response/SKILL) - Handle customer reviews
- [Pricing Strategy](../../ecommerce/pricing-strategy/SKILL) - Comprehensive pricing
- [Product Photography](../../content/product-photography/SKILL) - Image creation guide

---

## Appendix

### A: Amazon Fee Calculator Cheat Sheet

```
FBA Small Standard (up to 150g): £2.14
FBA Small Standard (150-400g): £2.27
FBA Small Standard (400g-900g): £2.59
FBA Large Standard (up to 150g): £2.73
FBA Large Standard (150-400g): £2.91
FBA Large Standard (400g-900g): £3.30
FBA Large Standard (900g-1.5kg): £3.68
FBA Large Standard (1.5kg-2kg): £4.00

Referral Fee (DIY & Tools): 15%
Referral Fee (Electronics): 7%
Referral Fee (Grocery): 8%
```

### B: Keyword Research Template

| Keyword | Search Vol | Difficulty | Tier | Location | PPC Bid | Notes |
|---------|------------|------------|------|----------|---------|-------|
| | | | | | | |

### C: Competitor Analysis Template

| ASIN | Brand | Price | Rating | Reviews | BSR | Strengths | Weaknesses |
|------|-------|-------|--------|---------|-----|-----------|------------|
| | | | | | | | |

### D: Launch Week Checklist

**Pre-Launch (Day -7):**
- [ ] Listing created and complete
- [ ] Images uploaded (7-9 images)
- [ ] A+ Content submitted and approved
- [ ] Backend keywords added
- [ ] Pricing set for Phase 1
- [ ] FBA inventory received
- [ ] PPC campaigns built (paused)

**Launch Day (Day 0):**
- [ ] Listing verified as active
- [ ] Search for title - confirm listing appears
- [ ] Enable PPC campaigns
- [ ] Share with internal team for verification

**Day 1-3:**
- [ ] Monitor PPC spend
- [ ] Check for any listing issues
- [ ] Verify order processing
- [ ] Begin review request timing

**Day 7:**
- [ ] First week performance review
- [ ] PPC search term report analysis
- [ ] Vine enrollment (if applicable)
- [ ] First bid adjustments

---

*Version 1.0.0 | Last Updated: 2025*
*For GTSE internal use - Confidential*
