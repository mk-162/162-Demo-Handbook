---
name: quick-seo-check
title: Quick SEO Health Check
description: 5-minute SEO sanity check for GTSE pages before publishing or quick diagnostics.
version: 2.0.0
author: GTSE AI Hub
tags: [seo, quick-check, publishing]
---

# Quick SEO Health Check

## Purpose

Fast pre-publish SEO checklist for any GTSE page. This is a **5-minute sanity check**, not a comprehensive audit.

**For deep SEO audits, use:** [Ecommerce SEO Audit](../ecommerce/seo-audit/SKILL)

## When to Use

- Before publishing any new page
- Quick check on existing pages
- Spot-checking after content updates
- NOT for comprehensive technical audits

## Inputs

| Input | Required | Description |
|-------|----------|-------------|
| `url` | ✅ | Page URL to check |
| `primary_keyword` | Optional | Target keyword to verify |

## 5-Point Quick Check

### 1. Title Tag ✅

| Check | Criteria | GTSE Standard |
|-------|----------|---------------|
| Length | Under 60 characters | Aim for 50-55 |
| Keyword | Primary keyword present | First 40 chars ideal |
| Branding | Ends with brand | "| GTSE" or "- GTSE Trade Supplies" |
| Uniqueness | Different from other pages | No duplicates |

**GTSE Title Examples:**
```
✅ Good: "Heavy Duty Cable Ties 300mm - Black Nylon | GTSE"
✅ Good: "PPE Buying Guide for Construction Sites | GTSE"
❌ Bad: "Cable Ties | GTSE Trade Supplies UK" (too generic)
❌ Bad: "Buy the Best Heavy Duty Industrial Grade Cable Ties..." (too long)
```

### 2. Meta Description ✅

| Check | Criteria |
|-------|----------|
| Length | 120-155 characters |
| Call-to-action | Includes action word |
| Value prop | States benefit |
| Keyword | Contains target keyword naturally |

**GTSE Meta Description Examples:**
```
✅ Good: "Shop heavy duty cable ties at trade prices. 300mm black nylon with 54kg tensile strength. Next-day UK delivery. Order now."
❌ Bad: "Cable ties for sale. Buy cable ties online at GTSE."
```

### 3. H1 Heading ✅

| Check | Criteria |
|-------|----------|
| Count | Exactly ONE H1 per page |
| Content | Matches page intent |
| Keyword | Contains primary keyword |
| Format | Clear, not stuffed |

**Quick Test:** Does the H1 answer "What is this page about?"

### 4. Images ✅

| Check | Criteria |
|-------|----------|
| Alt text | All images have descriptive alt |
| Relevance | Alt describes image, not keyword spam |
| File names | Descriptive (not IMG_001.jpg) |
| Size | Under 200KB for most images |

**GTSE Image Alt Examples:**
```
✅ Good: "Black nylon cable ties 300mm pack of 100"
✅ Good: "Worker installing cable ties on electrical conduit"
❌ Bad: "cable ties buy cable ties cheap cable ties UK"
❌ Bad: "image1"
```

### 5. Internal Links ✅

| Check | Criteria |
|-------|----------|
| Related products | 2-5 product links on content pages |
| Related content | 1-3 links to relevant guides/categories |
| Broken links | No 404s |
| Anchor text | Descriptive, not "click here" |

**GTSE Linking Rules:**
- Product pages → Related products + buying guide
- Category pages → Subcategories + featured products
- Blog posts → Products + related posts + category

## Quick Check Procedure

```
Step 1: Open page and view source (Ctrl+U)
Step 2: Find <title> tag - check length and keyword
Step 3: Find <meta name="description"> - check content
Step 4: Search for <h1> - verify only one exists
Step 5: Search for <img> tags - spot check alt attributes
Step 6: Click 3-5 internal links - verify they work
```

## Output Format

```markdown
## Quick SEO Check: [URL]
**Date:** [Date]
**Keyword:** [Target keyword]

### Results

| Check | Status | Notes |
|-------|--------|-------|
| Title | ✅/❌ | [Details] |
| Meta Description | ✅/❌ | [Details] |
| H1 | ✅/❌ | [Details] |
| Images | ✅/❌ | [Details] |
| Internal Links | ✅/❌ | [Details] |

### Quick Fixes Needed
1. [Fix 1]
2. [Fix 2]

### Overall: PASS / NEEDS FIXES
```

## Common GTSE Page Issues

| Issue | How to Spot | Fix |
|-------|-------------|-----|
| Duplicate titles | Multiple products same title | Add size/variant to title |
| Missing meta | Shows page content snippet in Google | Write custom description |
| Multiple H1s | Template issue | Fix theme template |
| Generic alt text | "product image" | Add product name + variant |
| Orphan pages | No internal links in | Add links from related pages |

## Related Skills

- [Ecommerce SEO Audit](../ecommerce/seo-audit/SKILL) - Comprehensive BigCommerce SEO audit
- [Content Strategy](../marketing/content-strategy/SKILL) - SEO content planning
- [Draft Blog Post](../draft-blog/SKILL) - SEO-optimized content creation
