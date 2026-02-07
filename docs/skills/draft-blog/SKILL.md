---
name: draft-blog-post
title: Draft Blog Post
description: Create SEO-optimized blog content for GTSE covering cable ties, PPE, safety equipment, and trade buying guides.
version: 2.0.0
author: GTSE AI Hub
tags: [content, seo, marketing, blog]
---

# Draft Blog Post

## Purpose

Create SEO-optimized blog content that ranks in Google, drives traffic, and converts visitors into trade customers. All content should serve GTSE's B2B audience: electricians, contractors, facility managers, and procurement teams.

## Inputs

| Input | Required | Description |
|-------|----------|-------------|
| `topic` | ✅ | Subject (e.g., "How to choose cable ties") |
| `keyword` | ✅ | Primary SEO keyword with search volume |
| `audience` | ✅ | Beginner / Expert / Procurement |
| `word_count` | Optional | Target length (default: 1,500-2,000) |
| `content_type` | Optional | Guide / Comparison / How-To / Listicle |

---

## GTSE Blog Topic Categories

### Cable Management (35% of content)

**High-Value Topics (with real specs):**
- "How to Choose the Right Cable Tie Size: Complete Guide"
- "Stainless Steel vs Nylon Cable Ties: 160kg vs 114kg Tensile Strength"
- "Cable Tie Tensile Strength Explained: From Standard to 160kg Heavy Duty"
- "UV Resistant Cable Ties: -40°C to 85°C Outdoor Performance"
- "Heavy Duty Cable Ties: 114kg (251lb) Industrial Applications"
- "316 Marine Grade Stainless Steel Ties: When Corrosion Resistance Matters"
- "Releasable Cable Ties: Pros, Cons, and Best Uses"
- "Biodegradable Cable Ties: Eco-Friendly Options for Agriculture"

**Long-Tail Opportunities:**
- "Cable ties for outdoor use: UV and temperature rated options"
- "Marine cable ties: 316 stainless steel for saltwater environments"
- "Best cable ties for oil & gas: High temperature resistance"
- "Heat shrink tubing: -55°C to 125°C specification guide"

**GTSE Spec References for Content:**
- Heavy Duty: 114kg (251lb) tensile strength
- Stainless Steel: 160kg (352lb) tensile, 316 marine grade
- Temperature ranges: -40°C to 85°C (nylon), -80°C to 538°C (stainless)
- Heat Shrink: -55°C to 125°C operating range

### PPE & Safety (30% of content)

**High-Value Topics:**
- "PPE Regulations UK 2025: What Employers Need to Know"
- "Choosing Work Gloves by Industry: Complete Guide"
- "Hi-Vis Clothing Standards Explained: EN ISO 20471"
- "Safety Glasses Categories: Which Do You Need?"
- "Hard Hat Expiry Dates: When to Replace PPE"

### Trade Buying & Procurement (20% of content)

**High-Value Topics:**
- "Bulk Buying Guide: Industrial Supplies"
- "Setting Up a Trade Account: Benefits and Process"
- "How to Reduce Supply Chain Costs: Industrial Consumables"
- "Single vs Multiple Suppliers: Pros and Cons"

### Industry Applications (15% of content)

**High-Value Topics (aligned with GTSE target sectors):**
- "Cable Management for Construction Sites: Heavy Duty Solutions"
- "Oil & Gas Cable Ties: Stainless Steel for Extreme Environments"
- "Automotive Cable Management: Engine Bay Heat Resistance"
- "Marine Cable Ties: 316 Grade for Offshore and Coastal"
- "Electrical Installation Cable Management Guide"
- "Aviation Cable Ties: Certification Requirements"
- "Medical/Pharmaceutical: Food-Grade and Traceability"
- "Agricultural Cable Ties: UV and Biodegradable Options"

**GTSE Target Industries:**
Construction, Electrical, Oil & Gas, Automotive, Aviation, Medical/Pharmaceutical, Marine, Agricultural, Audio-Visual

---

## Blog Post Structure Template

### Frontmatter

```yaml
---
title: "{{TITLE}}"
description: "{{META_DESCRIPTION_155_CHARS}}"
date: {{YYYY-MM-DD}}
author: GTSE Team
category: {{cable-management|ppe-safety|trade-buying|applications}}
tags: [{{tag1}}, {{tag2}}, {{tag3}}]
image: /images/blog/{{slug}}.jpg
---
```

### Content Structure

```markdown
# {{H1: Title with Primary Keyword}}

{{INTRO: 100-150 words}}
- Hook: Question, statistic, or relatable problem
- Problem statement: What reader is trying to solve
- Promise: What they'll learn
- Quick answer: For featured snippets

## {{H2: First Main Section}}

{{Content: 200-400 words}}
- Lead with the most important information
- Use bullet points for lists
- Include relevant specifications
- Add internal link to related product

### {{H3: Subsection if needed}}

{{Supporting detail}}

## {{H2: Second Main Section}}

{{Content: 200-400 words}}

[Continue with 2-5 H2 sections based on topic complexity]

## {{H2: Comparison Table}} (if applicable)

| Feature | Option A | Option B | Option C |
|---------|----------|----------|----------|
| {{Feature 1}} | {{Value}} | {{Value}} | {{Value}} |
| {{Feature 2}} | {{Value}} | {{Value}} | {{Value}} |

## Frequently Asked Questions

### {{Question 1}}?
{{Answer in 2-3 sentences}}

### {{Question 2}}?
{{Answer in 2-3 sentences}}

### {{Question 3}}?
{{Answer in 2-3 sentences}}

## Conclusion

{{Summary: 50-100 words}}
- Recap key points
- Recommend action
- Include CTA

{{CTA BLOCK}}
**Ready to order?** Browse our [{{product category}}](/category-link/) or [contact our trade team](/contact/) for bulk pricing.
```

---

## Writing Guidelines

### Tone & Style

| Attribute | GTSE Standard |
|-----------|---------------|
| Tone | Professional but accessible |
| Voice | Knowledgeable expert, trade-focused |
| Pronouns | "You" for reader, "We" for GTSE |
| Jargon | Use trade terms, explain if needed |
| Tagline | "Built for Business" |
| Ethos | Family business with global reach |

**GTSE Brand Voice:**
- Trade-focused, not consumer/DIY language
- Specific: real specs (114kg, 160kg, -40°C)
- Practical: solutions-oriented, no fluff
- Credible: 13+ years, 25,000+ SKUs, 3,000+ daily orders

### Readability Targets

| Metric | Target |
|--------|--------|
| Flesch-Kincaid Grade | 8-10 (accessible) |
| Sentence length | Average 15-20 words |
| Paragraph length | 2-4 sentences max |
| Section length | 200-400 words |

### SEO Requirements

| Element | Requirement |
|---------|-------------|
| Primary keyword | In title, H1, first 100 words, 2-3 H2s |
| Keyword density | 1-2% (natural, not forced) |
| Internal links | 3-5 to products, 1-2 to related posts |
| External links | 1-2 to authority sources (standards bodies, not competitors) |
| Image alt text | Descriptive, include keyword if natural |

---

## Content Type Templates

### Buying Guide Template

```markdown
# How to Choose [Product]: Complete Guide

Choosing the right [product] depends on [factors]. Here's what you need to know.

## Key Factors to Consider
### 1. [Factor: Size/Dimension]
### 2. [Factor: Material]
### 3. [Factor: Environment]
### 4. [Factor: Load/Capacity]

## [Product] Types Compared
[Comparison table]

## Quick Selection Guide
- **For [use case 1]:** Choose [product type]
- **For [use case 2]:** Choose [product type]

## Common Mistakes to Avoid
1. [Mistake 1]
2. [Mistake 2]

## FAQ
## Conclusion + CTA
```

### How-To Guide Template

```markdown
# How to [Action]: Step-by-Step Guide

[Brief intro: why this matters]

## What You'll Need
- [Item 1]
- [Item 2]

## Step 1: [Action]
[Instructions with detail]

## Step 2: [Action]
[Instructions with detail]

## Step 3: [Action]
[Instructions with detail]

## Tips for Best Results
- [Tip 1]
- [Tip 2]

## Troubleshooting Common Issues
| Problem | Cause | Solution |
|---------|-------|----------|

## Conclusion + CTA
```

### Comparison Template

```markdown
# [Option A] vs [Option B]: Which Should You Choose?

Quick answer: [One-sentence recommendation]

## Overview
| | [Option A] | [Option B] |
|---|---|---|
| Best for | [Use case] | [Use case] |
| Price range | [Range] | [Range] |
| Key advantage | [Advantage] | [Advantage] |

## [Option A] Explained
### Pros
### Cons
### Best for

## [Option B] Explained
### Pros
### Cons
### Best for

## Head-to-Head Comparison
[Detailed table]

## Our Recommendation
## FAQ
## Conclusion + CTA
```

---

## Procedure

### 1. Research (15 mins)
```
- Search Google for target keyword
- Analyze top 5 ranking pages
- Note: word count, structure, topics covered
- Identify gaps to fill
- Check GTSE product range for internal links
```

### 2. Outline (10 mins)
```
- Draft H1 with primary keyword
- List 4-6 H2 sections
- Note key points for each section
- Plan internal and external links
- Plan images/tables needed
```

### 3. Write (60-90 mins)
```
- Write intro with hook and promise
- Complete each section
- Add comparison tables where helpful
- Write FAQ section (3-5 questions)
- Write conclusion with CTA
```

### 4. Optimize (15 mins)
```
- Check keyword placement
- Add internal links to products
- Add external authority links
- Verify readability score
- Write meta description
- Add image alt text
```

### 5. Review (10 mins)
```
- Read aloud for flow
- Check all links work
- Verify facts and specifications
- Ensure GTSE brand voice
- Final spell/grammar check
```

---

## Output

Markdown file with:
- Complete frontmatter
- SEO-optimized content
- Internal links to GTSE products
- FAQ section with schema-ready Q&As
- Clear CTA

---

## Quality Checklist

Before submitting:
- [ ] Title under 60 characters with primary keyword
- [ ] Meta description 120-155 characters
- [ ] H1 matches title intent
- [ ] 3-5 internal links to products
- [ ] 1-2 external authority links
- [ ] FAQ section with 3+ questions
- [ ] Clear CTA at conclusion
- [ ] All images have alt text
- [ ] Readability score Grade 8-10
- [ ] Word count meets target

---

## Related Skills

- [Content Strategy](../marketing/content-strategy/SKILL) - Topic planning and keyword strategy
- [Quick SEO Check](../seo-audit/SKILL) - Pre-publish SEO verification
- [Social Content](../marketing/social-content/SKILL) - Repurposing blog for social
