# Amazon Review Response

Systematically manage Amazon customer reviews: monitor, categorize, respond appropriately, and escalate product issues to operations.

## When to Use

- Daily review monitoring (recommended)
- After product launches
- When negative reviews spike
- Before seasonal peaks (protect rating)
- Post quality control issues

## Inputs Required

| Input | Source | Required |
|-------|--------|----------|
| Brand Registry access | Seller Central | ✅ |
| Review notifications | Email alerts or API | ✅ |
| Customer Service scripts | `docs/customer-service/scripts.md` | Recommended |
| Product knowledge | Product specs | Recommended |
| Issue escalation contacts | Operations team | Recommended |

## Review Monitoring Workflow

### Step 1: Identify New Reviews

**Review Sources:**
- Seller Central → Brands → Customer Reviews
- Email alerts (set up in notification preferences)
- Third-party tools (FeedbackWhiz, Jungle Scout)

**Daily Check Routine:**
```
1. Filter: Last 7 days
2. Sort: Lowest rating first (1-star → 5-star)
3. Flag: Any mentioning defects, safety, wrong item
4. Queue: Responses needed
```

### Step 2: Categorize Reviews

| Rating | Category | Response Priority | Goal |
|--------|----------|-------------------|------|
| ⭐ 1-2 | Negative | 🔴 Within 24 hours | Resolve + remove if possible |
| ⭐ 3 | Neutral | 🟡 Within 48 hours | Engage, clarify, improve |
| ⭐ 4-5 | Positive | 🟢 Within 72 hours | Thank, build loyalty |

### Step 3: Response Templates

#### 🟢 Positive Reviews (4-5 Stars)

**Template - Simple Thank:**
```
Hi [Name],

Thank you for taking the time to share your experience with our [product]. 
We're thrilled to hear that [specific thing they mentioned]!

If you ever need any assistance or have questions about our other products, 
our UK-based team is here to help.

Best regards,
The GTSE Team
```

**Template - Detailed Positive:**
```
Hi [Name],

What a fantastic review - thank you! We're so pleased our [product] 
is [specific benefit they mentioned, e.g., "holding up well on the job site"].

Your feedback means a lot to our team here in the UK. If you're ever 
looking for [complementary product], we'd love to help again.

Cheers,
The GTSE Team
```

#### 🟡 Neutral Reviews (3 Stars)

**Template - Address Concern:**
```
Hi [Name],

Thank you for your honest feedback. We're glad our [product] 
[positive aspect they mentioned], and we're sorry to hear that 
[issue they raised].

We'd love to make this right. Could you contact us at [email/contact] 
so we can better understand your experience? We're always looking to improve.

Best regards,
The GTSE Team
```

**Template - Clarify Use Case:**
```
Hi [Name],

Thanks for your review! We noticed you mentioned [issue]. 

Just a quick tip: Our [product] is designed specifically for 
[correct use case]. For [their use case], our [alternative product] 
might be a better fit!

If you have any questions, we're happy to help at [contact].

Best,
The GTSE Team
```

#### 🔴 Negative Reviews (1-2 Stars)

**Template - Product Issue:**
```
Hi [Name],

We're truly sorry to hear about your experience with our [product]. 
This is not the quality we stand for, and we want to make it right.

Please contact us directly at [email] with your order number, and 
we'll arrange a replacement or full refund immediately - whichever 
you prefer.

We appreciate you bringing this to our attention and hope to 
restore your confidence in GTSE.

Sincerely,
The GTSE Customer Care Team
```

**Template - Wrong Expectations:**
```
Hi [Name],

Thank you for your feedback. We're sorry our [product] didn't meet 
your expectations.

We noticed you mentioned [their issue]. Our [product] is designed 
for [intended use], which may differ from [what they expected]. 
For [their need], we'd recommend [alternative].

We'd still like to help - please reach out to [contact] and we'll 
see what we can do.

Best regards,
The GTSE Team
```

**Template - Delivery Issue (Not Our Fault):**
```
Hi [Name],

We're so sorry about the delivery issues you experienced. While 
shipping is handled by Amazon/the carrier once it leaves our warehouse, 
we understand how frustrating delays can be.

We've checked your order and [provide relevant info]. If you need 
any further assistance, please contact us at [email] - we're here to help.

Best regards,
The GTSE Team
```

### Step 4: Response Best Practices

**DO:**
- ✅ Respond professionally and empathetically
- ✅ Acknowledge specific issues mentioned
- ✅ Offer solutions (replacement, refund, contact)
- ✅ Keep responses concise (3-5 sentences)
- ✅ Include contact information
- ✅ Personalize with their name and product

**DON'T:**
- ❌ Be defensive or argumentative
- ❌ Offer incentives for review changes (policy violation)
- ❌ Include links in responses
- ❌ Use ALL CAPS or excessive punctuation
- ❌ Copy-paste identical responses
- ❌ Blame the customer

### Step 5: Flag Product Issues for Operations

**Escalation Triggers:**

| Issue Type | Threshold | Action |
|------------|-----------|--------|
| Defect/breakage | 3+ mentions in 30 days | Quality control review |
| Wrong item sent | 2+ incidents | Warehouse check |
| Packaging damage | 3+ mentions | Packaging upgrade |
| Safety concern | 1 mention | Immediate investigation |
| Missing parts | 2+ mentions | QC process review |

**Escalation Report Template:**
```markdown
# Product Issue Escalation

**Product:** [ASIN + Name]
**Date:** [Date]
**Severity:** 🔴 High / 🟡 Medium / 🟢 Low

## Issue Summary
[Brief description]

## Customer Reports
| Date | Rating | Issue | Order # |
|------|--------|-------|---------|
| [Date] | ⭐⭐ | [Issue] | [#] |

## Pattern Analysis
[What's the common thread?]

## Recommended Action
[Specific steps for operations]

## Impact if Unaddressed
- Star rating trajectory: X.X → X.X
- Estimated revenue at risk: £X,XXX
```

## Output: Review Response Queue

```markdown
# Daily Review Response Queue

**Date:** [Date]
**Reviews Pending:** X
**Average Rating (7 days):** X.X ⭐

## 🔴 Urgent (1-2 Stars)
| Product | Rating | Issue | Draft Response |
|---------|--------|-------|----------------|
| [Name] | ⭐ | [Summary] | [Response] |

## 🟡 Moderate (3 Stars)
| Product | Rating | Issue | Draft Response |
|---------|--------|-------|----------------|
| [Name] | ⭐⭐⭐ | [Summary] | [Response] |

## 🟢 Thank (4-5 Stars)
| Product | Rating | Highlight | Draft Response |
|---------|--------|-----------|----------------|
| [Name] | ⭐⭐⭐⭐⭐ | [Nice quote] | [Response] |

## 🚨 Escalated to Operations
| Product | Issue | Reports | Severity |
|---------|-------|---------|----------|
| [Name] | [Issue] | X | 🔴 |
```

## Review Analytics Dashboard

Track weekly/monthly:
- New reviews by star rating
- Response rate and time
- Issues by category
- Rating trend (is it improving?)
- Competitor rating comparison

## Tools Used

- **Seller Central Brand Dashboard**: Review management
- **FeedbackWhiz**: Automated monitoring and alerts
- **Helium10 Review Insights**: Sentiment analysis
- **Slack/Teams**: Operations escalation

## Related Skills

- [Listing Audit](../listing-audit/SKILL) - Improve listings to set correct expectations
- [Competitor Monitor](../competitor-monitor/SKILL) - Compare review profiles
- [Handle Complaint](../handle-complaint/SKILL) - Customer service scripts
