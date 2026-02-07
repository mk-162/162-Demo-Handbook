---
title: Improvement Recommendations
---

# GTSE AI Hub: Improvement Recommendations

**Based on:** [Content Audit](AUDIT)
**Date:** January 2025

---

## Priority Matrix

| Priority | Impact | Effort | Timeline |
|----------|--------|--------|----------|
| 🔴 Critical | High business impact | 1-2 hours each | This week |
| 🟡 Important | Medium impact | 2-4 hours each | This month |
| 🟢 Enhancement | Nice to have | 1-2 hours each | Ongoing |

---

## 🔴 Critical Priority: Thin Skills Enhancement

### 1. Enhance `skills/seo-audit/SKILL.md`

**Current State:** 4 basic checks, no GTSE context, duplicates ecommerce version
**Action:** Either DELETE (redirecting to ecommerce/seo-audit) or make it a quick-check version

**Recommended Fix - Make it "Quick SEO Check":**

```markdown
---
name: quick-seo-check
title: Quick SEO Health Check
description: 5-minute SEO sanity check for any GTSE page before publishing
version: 2.0.0
tags: [seo, quick-check]
---

# Quick SEO Health Check

## Purpose
Fast pre-publish checklist. For deep audits, use [Ecommerce SEO Audit](ecommerce/seo-audit/SKILL).

## When to Use
- Before publishing any new page
- Quick check on existing pages
- NOT for comprehensive audits

## Inputs
- `url`: Page to check

## 5-Point Quick Check

### 1. Title Tag
- [ ] Under 60 characters
- [ ] Contains primary keyword
- [ ] Ends with "| GTSE" or similar brand

### 2. Meta Description
- [ ] Under 155 characters
- [ ] Contains call-to-action
- [ ] Compelling for click-through

### 3. H1 Heading
- [ ] Exactly one H1 on page
- [ ] Matches page intent
- [ ] Contains primary keyword

### 4. Images
- [ ] All images have alt text
- [ ] Alt text describes image (not keyword stuffing)

### 5. Internal Links
- [ ] Links to related products
- [ ] Links to related content
- [ ] No broken links

## Output
Pass/Fail for each check with specific fixes needed.

## Related
- [Full SEO Audit](ecommerce/seo-audit/SKILL) - Comprehensive audit
- [Content Strategy](marketing/content-strategy/SKILL) - SEO content planning
```

**Effort:** 1 hour

---

### 2. Enhance `skills/draft-blog/SKILL.md`

**Current State:** ~120 words, too generic
**Action:** Expand with GTSE topics, templates, and detailed procedure

**Enhancement Content to Add:**

```markdown
## GTSE Blog Topics by Category

### Cable Management (35% of content)
- "How to Choose the Right Cable Tie Size"
- "Stainless Steel vs Nylon Cable Ties: Complete Comparison"
- "Cable Tie Tensile Strength Explained"
- "UV Resistant Cable Ties: When You Need Them"

### PPE & Safety (30% of content)
- "PPE Regulations UK: [Year] Update"
- "Choosing Work Gloves by Industry"
- "Hi-Vis Clothing Standards Explained"

### Trade Buying (20% of content)
- "Bulk Buying Guide: Industrial Supplies"
- "Setting Up a Trade Account: What to Expect"

### Industry Applications (15% of content)
- "Cable Management for Data Centres"
- "Construction Site Safety Checklist"

## Blog Post Template

### Frontmatter
```yaml
---
title: {{TITLE}}
description: {{META_DESCRIPTION}}
date: {{DATE}}
author: GTSE Team
category: {{CATEGORY}}
tags: [{{TAG1}}, {{TAG2}}]
---
```

### Structure
1. **H1: Title with Primary Keyword**
2. **Intro (100-150 words):** Hook + problem + what they'll learn
3. **H2 sections (2-5):** Main content points
4. **H2: FAQ Section (3-5 questions)**
5. **H2: Conclusion + CTA**

### GTSE Blog Checklist
- [ ] Primary keyword in title
- [ ] 1,500-2,500 words for guides
- [ ] 3-5 internal links to products
- [ ] 1-2 internal links to related posts
- [ ] 1 external authority link
- [ ] Images with alt text
- [ ] Clear CTA at end
```

**Effort:** 2 hours

---

### 3. Enhance `skills/competitor-research/SKILL.md`

**Current State:** Basic SWOT only, no competitor list
**Action:** Merge with or reference ecommerce/competitor-analyzer

**Recommended Fix - Make it a Wrapper:**

```markdown
# Competitor Research (Quick)

## Purpose
Fast competitive intelligence for specific questions. For comprehensive analysis, use [Competitor Analyzer](ecommerce/competitor-analyzer/SKILL).

## Quick Research Framework

### Price Check (15 minutes)
1. Identify 3 key products to compare
2. Check prices at: RS, Screwfix, Amazon, Cable Ties Direct
3. Record: Price, quantity, delivery cost
4. Calculate: Price per unit

### Product Range Check (10 minutes)
1. Does competitor have the product we're considering?
2. How many variants do they offer?
3. What's their bestseller in category?

### Website Quick Scan (10 minutes)
1. What's their homepage headline promise?
2. Do they have trade accounts?
3. What's their delivery offer?
4. Trust signals (reviews, certifications)?

## Output
Quick comparison table + 3 key findings.

## Related
- [Full Competitor Analyzer](ecommerce/competitor-analyzer/SKILL)
```

**Effort:** 1 hour

---

### 4. Enhance `skills/generate-leads/SKILL.md`

**Current State:** Generic 4-step procedure
**Action:** Add GTSE segments, targeting criteria, tool instructions

**Enhancement Content:**

```markdown
## GTSE Target Segments

### Segment 1: Electrical Contractors
- **Company size:** 5-50 employees
- **Location:** UK-wide
- **Signals:** NICEIC/ECA accredited
- **Keywords:** electrical contractor, electrician, wiring
- **Products they buy:** Cable ties, trunking, clips

### Segment 2: Facilities Management
- **Company size:** 10-200 employees
- **Location:** UK commercial areas
- **Signals:** Multiple site locations
- **Keywords:** facilities management, building maintenance
- **Products they buy:** PPE, consumables, safety equipment

### Segment 3: Construction Companies
- **Company size:** 20-500 employees
- **Location:** UK-wide
- **Signals:** Active projects, hiring
- **Keywords:** construction, building contractor
- **Products they buy:** Site equipment, safety, fixings

## Search Strategies

### LinkedIn Sales Navigator
```
Title: (Purchasing OR Procurement OR Buyer OR "Operations Manager")
Industry: Construction OR Electrical OR Manufacturing
Company size: 11-500
Location: United Kingdom
```

### Google Search
```
site:linkedin.com/company "electrical contractor" "UK"
site:companieshouse.gov.uk SIC:43210 (electrical installation)
"facilities management" "contact us" UK
```

## Output Format
CSV with: Company, Contact Name, Title, Email, LinkedIn, Website, Segment
```

**Effort:** 2 hours

---

### 5. Enhance `skills/handle-complaint/SKILL.md`

**Current State:** References external scripts, no actual templates
**Action:** Add response templates, escalation criteria, GTSE policies

**Enhancement Content:**

```markdown
## Complaint Categories & Responses

### Category 1: Late Delivery
**Severity:** Medium
**Response Time:** 4 hours

**Template:**
```
Hi {{NAME}},

I'm really sorry your order arrived late - I understand how frustrating that is, especially when you're waiting on supplies for a job.

I've looked into this, and [REASON: carrier delay / stock issue / etc.].

To make this right:
- [COMPENSATION: £X credit / discount code / free delivery on next order]

Your order {{ORDER_NUMBER}} [STATUS: has now been delivered / is on its way].

Is there anything else I can help with?

Best regards,
[NAME] - GTSE Customer Service
```

### Category 2: Wrong Item
**Severity:** High
**Response Time:** 2 hours

**Template:**
```
Hi {{NAME}},

I apologise - we sent you the wrong item. That's completely our mistake.

Here's what I've done:
1. Arranged for the correct item to be dispatched TODAY
2. Emailed you a free returns label for the wrong item
3. Added a {{DISCOUNT}} code for your next order as an apology

You should receive the correct item by {{DATE}}.

Please accept my apologies for the inconvenience.

[NAME] - GTSE Customer Service
```

### Category 3: Damaged Item
**Severity:** High
**Response Time:** 2 hours

### Category 4: Quality Issue
**Severity:** Critical (escalate)
**Response Time:** 1 hour

## Escalation Matrix

| Issue | Escalate When | To Whom |
|-------|---------------|---------|
| Refund > £100 | Always | Manager |
| Repeat complaint | 2nd occurrence | Manager |
| Legal threat | Always | Director |
| Social media | Always | Marketing + Manager |
| Safety issue | Always | Director + QA |

## Compensation Guidelines

| Issue | Standard Compensation |
|-------|----------------------|
| Late 1-2 days | Apology only |
| Late 3+ days | 10% discount code |
| Wrong item | Free returns + 10% off |
| Damaged | Replacement + 10% off |
| Quality issue | Full refund option |
```

**Effort:** 2 hours

---

### 6. Fix Skills Index

**Current State:** Missing 5 skill entries
**Action:** Update `docs/skills/index.md`

**Add these entries:**

```markdown
### Quick Tools & Utilities
*   **[A/B Test Setup](ab-test-setup/SKILL)**: Configure and track website experiments.
*   **[Draft Blog Post](draft-blog/SKILL)**: Create SEO-optimized blog content.
*   **[Quick SEO Check](seo-audit/SKILL)**: Pre-publish SEO sanity check.

### Research & Analysis
*   **[Competitor Research](competitor-research/SKILL)**: Quick competitive intelligence.
*   **[Generate B2B Leads](generate-leads/SKILL)**: Build targeted prospect lists.

### Customer Service
*   **[Handle Complaint](handle-complaint/SKILL)**: Respond to customer issues with templates.
```

**Effort:** 30 minutes

---

## 🟡 Important Priority: Consistency & Gaps

### 7. Standardize Frontmatter Across All Skills

**Issue:** Mixed frontmatter formats
**Action:** Apply consistent schema to all skills

**Standard Format:**
```yaml
---
name: skill-slug
title: Human Readable Title
description: One-line description
version: 1.0.0
author: GTSE AI Hub
tags: [category, relevant-tags]
globs: ["*.md"]
---
```

**Effort:** 2 hours (batch update)

---

### 8. Remove/Consolidate Duplicate Skills

**Duplicates Found:**
- `skills/seo-audit/` vs `skills/ecommerce/seo-audit/` → Keep ecommerce version
- `skills/create-page/` vs `skills/meta/update-kb/` → Keep meta version

**Action:** 
1. Redirect root-level skills to category versions
2. Or make them "quick" versions that reference full skills

**Effort:** 1 hour

---

### 9. Add Missing Playbooks

**Gaps Identified (from common workflows):**

| Playbook Needed | Business Impact | Effort |
|-----------------|-----------------|--------|
| Returns & RMA Handling | High | 2 hours |
| Seasonal Sale Setup | Medium | 2 hours |
| New Employee Onboarding | Medium | 3 hours |
| Amazon Review Request | Low | 1 hour |

**Effort:** 8 hours total

---

### 10. Add Missing Templates

**Gaps Identified:**

| Template Needed | Use Case | Priority |
|-----------------|----------|----------|
| Customer Complaint Response | CS team | 🔴 High |
| Trade Account Application | Sales team | 🟡 Medium |
| Product Return Request | Operations | 🟡 Medium |
| Meeting Follow-Up Email | Sales team | 🟢 Low |

**Effort:** 4 hours total

---

## 🟢 Enhancement Priority: Nice to Have

### 11. Add "Related Skills" to All Skills

**Issue:** Only 52% of skills link to related skills
**Action:** Add Related Skills section to all

**Effort:** 2 hours

---

### 12. Add Skill Usage Examples

**Issue:** Some skills lack concrete examples
**Action:** Add "Example Invocation" section showing:
- Sample input
- Expected output
- Common variations

**Effort:** 3 hours

---

### 13. Create Skill Dependency Diagram

**Action:** Add visual diagram showing how skills connect

```
┌─────────────────┐
│   find-knowledge │ ← Search first
└────────┬────────┘
         ↓
┌─────────────────┐
│  competitor-    │ ← Research context
│  analyzer       │
└────────┬────────┘
         ↓
┌─────────────────┐
│  content-       │ ← Plan content
│  strategy       │
└────────┬────────┘
         ↓
┌─────────────────┐
│   draft-blog    │ ← Create content
└────────┬────────┘
         ↓
┌─────────────────┐
│   update-kb     │ ← Save & publish
└─────────────────┘
```

**Effort:** 1 hour

---

## New Skills to Create

### High Priority (Business Impact)

| Skill | Purpose | Effort |
|-------|---------|--------|
| `inventory-alert-handler` | Respond to low stock / overstock | 2 hours |
| `pricing-updater` | Update prices across channels | 2 hours |
| `review-analyzer` | Extract insights from reviews | 2 hours |

### Medium Priority (Operational Efficiency)

| Skill | Purpose | Effort |
|-------|---------|--------|
| `email-campaign-creator` | Klaviyo email drafting | 2 hours |
| `bulk-order-processor` | Handle large B2B orders | 2 hours |
| `product-bundler` | Create bundle recommendations | 1 hour |

### Low Priority (Nice to Have)

| Skill | Purpose | Effort |
|-------|---------|--------|
| `social-post-scheduler` | Batch social content | 1 hour |
| `warranty-claim-handler` | Process warranty requests | 1 hour |

---

## New Playbooks to Create

### High Priority

1. **Returns & Refunds Processing**
   - Customer request handling
   - Return authorization
   - Refund processing
   - Quality issue escalation

2. **Trade Account Setup**
   - Application review
   - Credit check process
   - Account creation
   - Welcome sequence

### Medium Priority

3. **Inventory Reorder Process**
   - Stock level monitoring
   - Supplier ordering
   - Lead time tracking
   - Emergency restock

4. **Amazon Advertising Launch**
   - New product PPC setup
   - Campaign structure
   - Keyword research
   - First 30 days optimization

---

## Implementation Roadmap

### Week 1 (Critical)
- [ ] Enhance 3 thin skills (SEO, blog, complaint)
- [ ] Update skills index with missing entries
- [ ] Add Customer Complaint Response template

### Week 2 (Critical + Important)
- [ ] Enhance remaining 3 thin skills
- [ ] Standardize frontmatter across all skills
- [ ] Remove/consolidate duplicate skills

### Week 3-4 (Important)
- [ ] Create 2 missing playbooks
- [ ] Create 2 missing templates
- [ ] Add Related Skills to all skills

### Month 2 (Enhancement)
- [ ] Create 3 new high-priority skills
- [ ] Add example sections to all skills
- [ ] Create skill dependency diagram

---

## Success Metrics

After implementation:

| Metric | Current | Target |
|--------|---------|--------|
| Skills meeting quality bar | 74% | 95% |
| Skills with GTSE examples | 61% | 90% |
| Skills with Related links | 52% | 100% |
| Index file completeness | 67% | 100% |
| Average skill word count | ~800 | ~1,200 |

---

*Review this document quarterly and update based on business needs and feedback.*
