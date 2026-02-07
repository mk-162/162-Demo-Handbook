# Amazon Listing Audit

Comprehensive audit of Amazon product listings against best practices, generating actionable improvement scores and recommendations.

## When to Use

- Before product launch
- Quarterly listing health checks
- When sales decline unexpectedly
- After competitor analysis reveals gaps
- Before peak selling seasons (Q4, Prime Day)

## Inputs Required

| Input | Source | Required |
|-------|--------|----------|
| ASIN or product URL | User provides | ✅ |
| Brand guidelines | `docs/brand/` | Optional |
| Target keywords | Helium10/DataDive export | Optional |
| Competitor ASINs | For benchmarking | Optional |

## Audit Sections

### 1. Title Audit (Max Score: 20)

**Check Against:**
- [ ] Length ≤ 200 characters (Amazon limit)
- [ ] Format follows: `[Brand] [Product] [Feature 1] [Feature 2] [Size/Qty] [Color]`
- [ ] Primary keyword in first 80 characters (mobile visibility)
- [ ] No promotional language ("Best Seller", "Free Shipping")
- [ ] No special characters (™ ® allowed if registered)
- [ ] Title case, not ALL CAPS

**GTSE Example - Cable Ties (with real specs):**
```
✅ Good: "GTSE Heavy Duty Cable Ties 300mm x 4.8mm - Black Nylon 114kg Tensile Strength UV Resistant (Pack of 100)"
✅ Good: "GTSE Stainless Steel Cable Ties 300mm - Marine Grade 316 Metal Zip Ties 160kg Tensile (Pack of 50)"
❌ Bad: "BEST CABLE TIES!!! - Heavy Duty Zip Ties Black 300mm FREE DELIVERY!!!!"
```

**Key GTSE Specs to Include:**
- Heavy Duty: 114kg (251lb) tensile strength
- Stainless Steel: 160kg (352lb) tensile strength
- Temperature: -40°C to 85°C (standard), -80°C to 538°C (stainless)
- Material: Nylon 66, 316 Marine Grade Stainless

**Scoring:**
| Criteria | Points |
|----------|--------|
| Correct length | 4 |
| Proper format | 4 |
| Primary keyword placement | 4 |
| No policy violations | 4 |
| Brand included | 4 |

### 2. Bullet Points Audit (Max Score: 25)

**Check Each Bullet:**
- [ ] Uses all 5 bullet slots
- [ ] Each ≤ 500 characters (250 recommended for mobile)
- [ ] CAPITAL BENEFIT PREFIX format: "PROFESSIONAL GRADE: ..."
- [ ] Includes specifications (dimensions, weight, material)
- [ ] Addresses customer pain points
- [ ] Contains secondary keywords naturally
- [ ] No competitor mentions or prohibited claims

**GTSE Bullet Structure Template:**
```
1. PRIMARY BENEFIT: "INDUSTRIAL STRENGTH 114KG TENSILE..." 
2. QUALITY/MATERIAL: "UV & EXTREME TEMPERATURE RESISTANT: -40°C to 85°C..."
3. SPECIFICATIONS: "PRECISION DIMENSIONS: 300mm x 4.8mm, bundle diameter up to 80mm..."
4. USE CASES: "TRUSTED BY TRADE: Construction, electrical, automotive, marine..."
5. TRUST/GUARANTEE: "GTSE - BUILT FOR BUSINESS: UK-based, 3,000+ daily orders, trade accounts available..."
```

**Real GTSE Specs to Reference:**
- Heavy Duty: 114kg (251lb) tensile
- Stainless Steel: 160kg (352lb) tensile, 316 marine grade
- Heat Shrink: -55°C to 125°C
- Company: 25,000+ SKUs, 3,000+ orders daily
- Trade: 30-day terms, £75 free UK delivery, $500 free US shipping

**Scoring:**
| Criteria | Points |
|----------|--------|
| All 5 bullets used | 5 |
| Proper formatting | 5 |
| Benefits-focused | 5 |
| Specs included | 5 |
| Keyword optimization | 5 |

### 3. Image Audit (Max Score: 25)

**Main Image Requirements:**
- [ ] Pure white background (RGB 255,255,255)
- [ ] Product fills 85%+ of frame
- [ ] High resolution (1500x1500px minimum for zoom)
- [ ] No text, logos, or watermarks on product
- [ ] Accurate color representation

**Secondary Images (7+ slots):**
| Slot | Purpose | Check |
|------|---------|-------|
| 2 | Infographic with dimensions | ✅/❌ |
| 3 | Lifestyle/in-use | ✅/❌ |
| 4 | Scale comparison | ✅/❌ |
| 5 | Package contents | ✅/❌ |
| 6 | Multi-angle view | ✅/❌ |
| 7 | Feature callouts | ✅/❌ |
| 8+ | Video if available | ✅/❌ |

**GTSE Image Checklist - Cable Ties:**
- Infographic: Show "114kg tensile strength" or "160kg tensile" prominently
- Infographic: Include "-40°C to 85°C" temperature range
- Lifestyle: Electrician on construction site, mechanic in engine bay
- Scale: Next to a ruler or hand for size reference
- Application: Show marine/outdoor for stainless steel range
- Package: Bag/box as customer will receive it

**GTSE Image Checklist - Stainless Steel Ties:**
- Main: Show steel finish and ball-lock mechanism
- Infographic: "160kg (352lb) tensile" + "316 Marine Grade" badges
- Lifestyle: Marine, offshore, or high-temp application
- Application: Show corrosion resistance context

**Scoring:**
| Criteria | Points |
|----------|--------|
| Main image compliant | 5 |
| 7+ images used | 5 |
| Infographic present | 5 |
| Lifestyle/use image | 5 |
| Video included | 5 |

### 4. A+ Content Audit (Max Score: 15)

**Check for:**
- [ ] A+ Content enabled (Brand Registry required)
- [ ] Brand story module present
- [ ] Comparison chart vs other products in range
- [ ] High-quality lifestyle imagery
- [ ] Mobile-optimized layout
- [ ] No duplicate title/bullet content
- [ ] Cross-sell modules for complementary products

**Scoring:**
| Criteria | Points |
|----------|--------|
| A+ enabled | 5 |
| Brand story present | 3 |
| Comparison chart | 3 |
| Mobile optimization | 2 |
| Cross-sell modules | 2 |

### 5. Backend Search Terms (Max Score: 10)

**Check:**
- [ ] All 250 bytes used (not characters - check actual byte count)
- [ ] No repeated words from title/bullets
- [ ] Includes misspellings customers make
- [ ] Includes synonyms and alternate names
- [ ] No commas needed (space-separated)
- [ ] No ASINs or competitor brand names (policy violation)

**GTSE Example - Cable Ties Backend:**
```
zip tie cable wrap wire tidy nylon strap bundle wire tie electric cable 
tidy construction site professional tradesman electrician plumber wire 
management organizer bundler fastener tie wrap zipties cabletie
```

**Scoring:**
| Criteria | Points |
|----------|--------|
| Bytes fully utilized | 4 |
| No word repetition | 2 |
| Synonyms/misspellings | 2 |
| Policy compliant | 2 |

### 6. Pricing Analysis (Max Score: 5)

**Compare:**
- [ ] Price vs top 5 competitors for same quantity
- [ ] Price per unit calculation
- [ ] Shipping included (FBA vs FBM)
- [ ] Coupon/deal availability
- [ ] Subscribe & Save enabled if applicable

**Scoring:**
| Criteria | Points |
|----------|--------|
| Competitively priced | 2 |
| Value proposition clear | 2 |
| S&S enabled | 1 |

## Output: Audit Report

```markdown
# Amazon Listing Audit Report

**ASIN:** B0XXXXXXXXX
**Product:** GTSE Heavy Duty Cable Ties 300mm
**Audit Date:** 2025-01-XX
**Auditor:** [AI/Human]

## Overall Score: XX/100

### Section Scores
| Section | Score | Max | Status |
|---------|-------|-----|--------|
| Title | XX | 20 | 🟢/🟡/🔴 |
| Bullets | XX | 25 | 🟢/🟡/🔴 |
| Images | XX | 25 | 🟢/🟡/🔴 |
| A+ Content | XX | 15 | 🟢/🟡/🔴 |
| Backend | XX | 10 | 🟢/🟡/🔴 |
| Pricing | XX | 5 | 🟢/🟡/🔴 |

### Priority Fixes (High Impact)
1. [Issue] → [Specific action]
2. [Issue] → [Specific action]

### Quick Wins (Low Effort)
1. [Action]
2. [Action]

### Long-Term Improvements
1. [Action]
2. [Action]
```

## Score Thresholds

| Score | Rating | Action |
|-------|--------|--------|
| 90-100 | 🟢 Excellent | Maintain, minor tweaks |
| 70-89 | 🟡 Good | Optimize within 2 weeks |
| 50-69 | 🟠 Needs Work | Prioritize fixes this week |
| 0-49 | 🔴 Critical | Stop ads, fix immediately |

## Tools Used

- **Helium10 Cerebro**: Keyword research
- **DataDive**: Competitor pricing
- **Sellerboard**: Profit margin calc
- **Canva/Photoshop**: Image editing

## Related Skills

- [PPC Optimizer](../ppc-optimizer/SKILL) - Optimize ads after listing is fixed
- [Competitor Monitor](../competitor-monitor/SKILL) - Benchmark against competition
- [Review Response](../review-response/SKILL) - Manage resulting review engagement
