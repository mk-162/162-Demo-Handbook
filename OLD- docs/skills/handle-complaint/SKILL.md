---
name: handle-customer-complaint
title: Handle Customer Complaint
description: De-escalate customer complaints and generate appropriate responses with compensation guidelines for GTSE trade and retail customers.
version: 2.0.0
author: GTSE AI Hub
tags: [support, customer-service, escalation]
---

# Handle Customer Complaint

## Purpose

De-escalate customer complaints, retain customers, and protect GTSE's reputation. This skill provides response templates, compensation guidelines, and escalation criteria for the customer service team.

## Inputs

| Input | Required | Description |
|-------|----------|-------------|
| `complaint_text` | ✅ | What the customer said (email/message) |
| `order_id` | ✅ | Order reference number |
| `issue_type` | ✅ | Late / Damaged / Wrong / Quality / Missing |
| `customer_type` | Optional | Trade account / Retail / First-time |
| `order_value` | Optional | For compensation calculation |

---

## Complaint Categories

### Category 1: Late Delivery

**Severity:** Medium
**Response SLA:** 4 hours
**Root Causes:** Carrier delay, stock issue, address problem

| Delay | Compensation | Trade Account |
|-------|--------------|---------------|
| 1-2 days | Apology only | Apology only |
| 3-5 days | 10% discount code | 10% off next order |
| 5+ days | 15% discount + free delivery | 15% + account credit |
| Critical (job delayed) | Case by case | Priority handling + credit |

**Response Template - Standard Late:**

```
Subject: Re: Order {{ORDER_ID}} - Apologies for the delay

Hi {{FIRST_NAME}},

I'm really sorry your order arrived late - I completely understand how frustrating that is, especially when you're counting on supplies for a job.

I've looked into this, and {{ROOT_CAUSE: the carrier experienced unexpected delays / we had a temporary stock shortage / there was an address issue}}.

Your order {{STATUS: has now been delivered / is on its way - tracking: {{TRACKING_LINK}} / is being dispatched today}}.

{{IF COMPENSATION}}
To make this right, here's a {{DISCOUNT}}% discount code for your next order: {{CODE}}
{{/IF}}

Is there anything else I can help with?

Best regards,
{{AGENT_NAME}}
GTSE Customer Service
```

---

### Category 2: Wrong Item Sent

**Severity:** High
**Response SLA:** 2 hours
**Root Causes:** Pick error, system error, labelling issue

**Compensation:**
- Free returns (prepaid label)
- Correct item sent same-day (if before 2pm)
- 10% discount code for inconvenience

**Response Template - Wrong Item:**

```
Subject: Re: Order {{ORDER_ID}} - Sorting this out now

Hi {{FIRST_NAME}},

I apologise - we sent you the wrong item. That's completely our mistake, and I'm sorting it out right now.

Here's what I've done:
1. ✅ Arranged for the correct item ({{CORRECT_ITEM}}) to be dispatched TODAY
2. ✅ Emailed you a prepaid returns label for the wrong item
3. ✅ Added a 10% discount code for your next order: {{CODE}}

You should receive the correct item by {{DELIVERY_DATE}}.

For the return, just pop the wrong item in any box and drop it at your nearest {{CARRIER: Royal Mail / DPD / Evri}} point - no rush, whenever suits you.

Please accept my sincere apologies for the mix-up.

{{AGENT_NAME}}
GTSE Customer Service
```

---

### Category 3: Damaged Item

**Severity:** High
**Response SLA:** 2 hours
**Root Causes:** Transit damage, packaging failure, warehouse damage

**Compensation:**
- Full replacement OR full refund (customer choice)
- 10% discount code
- No return required for low-value items (<£20)

**Response Template - Damaged Item:**

```
Subject: Re: Order {{ORDER_ID}} - Replacing your damaged item

Hi {{FIRST_NAME}},

I'm sorry to hear your order arrived damaged - that's not the standard we hold ourselves to.

{{IF PHOTO_REQUESTED}}
Could you send me a quick photo of the damage? This helps us improve our packaging and claim from the carrier.
{{/IF}}

{{IF REPLACEMENT}}
I've arranged a replacement to be sent out today. You should receive it by {{DATE}}.

{{IF RETURN_REQUIRED}}
For the damaged item, I've attached a prepaid returns label - just send it back when convenient.
{{ELSE}}
No need to return the damaged item - please dispose of it however suits you.
{{/IF}}
{{/IF}}

{{IF REFUND}}
I've processed a full refund of £{{AMOUNT}} to your original payment method. This should appear within 3-5 business days.
{{/IF}}

As an apology, here's 10% off your next order: {{CODE}}

Really sorry about this. Let me know if there's anything else I can do.

{{AGENT_NAME}}
GTSE Customer Service
```

---

### Category 4: Quality Issue

**Severity:** Critical (Escalate)
**Response SLA:** 1 hour
**Root Causes:** Manufacturing defect, specification mismatch, supplier issue

**Process:**
1. Acknowledge and apologize immediately
2. Request photos/details
3. Escalate to QA team
4. Offer replacement OR refund
5. Log for supplier review

**Response Template - Quality Issue:**

```
Subject: Re: Order {{ORDER_ID}} - Quality concern

Hi {{FIRST_NAME}},

Thank you for letting us know about this quality issue - this is really important feedback.

I'm sorry the {{PRODUCT}} didn't meet expectations. We take quality seriously, and I want to understand exactly what happened.

Could you share:
- A photo of the issue (if possible)
- What specifically wasn't right?
- How many items in the pack were affected?

In the meantime, I'd like to offer you:
[ ] A full replacement dispatched today
[ ] A full refund of £{{AMOUNT}}

Just let me know which you'd prefer.

I'm also escalating this to our quality team to investigate. We appreciate you bringing this to our attention - it helps us maintain standards.

{{AGENT_NAME}}
GTSE Customer Service

---
INTERNAL: Escalate to QA. Log product: {{SKU}}, Batch: {{BATCH_IF_KNOWN}}
```

---

### Category 5: Missing Item from Order

**Severity:** High
**Response SLA:** 2 hours
**Root Causes:** Pick error, system error, multiple package confusion

**Response Template - Missing Item:**

```
Subject: Re: Order {{ORDER_ID}} - Missing item

Hi {{FIRST_NAME}},

I'm sorry to hear part of your order was missing. Let me sort that out right now.

{{IF SEPARATE_PACKAGE}}
Good news - I can see the {{MISSING_ITEM}} was dispatched separately and should arrive by {{DATE}}. Here's the tracking: {{TRACKING}}
{{/IF}}

{{IF PICK_ERROR}}
I apologise - looks like we missed the {{MISSING_ITEM}} when packing your order. I've arranged for it to be dispatched today, arriving by {{DATE}}.
{{/IF}}

To apologise for the inconvenience, I've added free delivery to your next order - just use code: {{CODE}}

Really sorry about this. Let me know if anything else is missing.

{{AGENT_NAME}}
GTSE Customer Service
```

---

## Escalation Matrix

### When to Escalate

| Trigger | Escalate To | Response Time |
|---------|-------------|---------------|
| Refund > £100 | Team Lead / Manager | 30 mins |
| Repeat complaint (2nd time same issue) | Manager | 30 mins |
| Threat of legal action | Director + Legal | Immediate |
| Social media complaint | Marketing + Manager | 30 mins |
| Safety concern | Director + QA | Immediate |
| Trade account churn risk | Account Manager | 1 hour |
| Press / media inquiry | Marketing Director | Immediate |

### Escalation Template

```
INTERNAL ESCALATION

Customer: {{NAME}} ({{EMAIL}})
Order: {{ORDER_ID}} - Value: £{{VALUE}}
Account Type: {{Trade/Retail}}

Issue: {{BRIEF_DESCRIPTION}}

Previous contact: {{YES/NO - details}}

Escalation reason: {{REASON}}

Current status: {{WHAT_YOU'VE_DONE}}

Recommendation: {{YOUR_SUGGESTION}}

Urgency: {{HIGH/MEDIUM}}
```

---

## Compensation Guidelines

### Standard Compensation

| Issue | Retail Customer | Trade Account |
|-------|-----------------|---------------|
| Minor delay (1-2 days) | Apology | Apology |
| Significant delay (3+ days) | 10% code | 10% next order |
| Wrong item | 10% code + free return | 10% + free return |
| Damaged item | 10% code | Account credit 10% |
| Quality issue | Refund + 15% code | Refund + account review |
| Multiple issues | 20% code | Account credit + call |

### Trade Account Special Handling

For trade accounts, consider:
- Account history (order frequency, value)
- Relationship length
- Strategic importance
- Whether issue affects their customer

**High-value trade accounts:** Involve Account Manager for complaints over £50 or repeat issues.

---

## Sentiment Analysis Guide

### Mild Frustration
**Indicators:** Polite language, requests resolution, single exclamation marks
**Approach:** Standard response, genuine apology, quick resolution

### Moderate Anger
**Indicators:** Strong language, multiple complaints listed, demands
**Approach:** Extra empathy, phone call offer, proactive compensation

### Severe/Furious
**Indicators:** ALL CAPS, threats (legal, review, social media), profanity
**Approach:** Escalate immediately, manager call-back, premium resolution

### Assessment Questions
1. How many times have they contacted us about this?
2. Is their business affected (trade customer on a job)?
3. Have we failed them before?
4. Are they a high-value customer?

---

## Response Quality Checklist

Before sending:
- [ ] Used customer's name
- [ ] Acknowledged their specific issue
- [ ] Apologized genuinely (not "sorry for any inconvenience")
- [ ] Explained what happened (briefly, no excuses)
- [ ] Stated clear resolution + timeline
- [ ] Offered appropriate compensation
- [ ] Provided direct contact for follow-up
- [ ] Proofread for tone and errors

---

## Procedure

1. **Analyze Complaint**
   - Read fully, identify all issues mentioned
   - Check order history and previous contacts
   - Categorize by issue type

2. **Assess Severity**
   - Use sentiment analysis guide
   - Check if escalation needed
   - Identify customer type (trade/retail/new)

3. **Investigate**
   - Check order status, tracking
   - Review warehouse notes
   - Identify root cause

4. **Select Template**
   - Choose appropriate category template
   - Customize with specifics

5. **Determine Compensation**
   - Apply guidelines based on issue + customer type
   - Get approval if exceeds limits

6. **Personalize Response**
   - Add customer name, order details
   - Reference their specific complaint
   - Adjust tone to match severity

7. **Send & Log**
   - Send response
   - Log in CRM with category + resolution
   - Set follow-up if needed

---

## Output

Draft email response with:
- Personalized greeting
- Specific acknowledgment of issue
- Clear resolution + timeline
- Appropriate compensation
- Follow-up option

---

## Related Skills

- [Customer Service Scripts](../../customer-service/scripts) - Standard responses
- [B2B Outreach](../b2b/cold-outreach/SKILL) - Win-back for churned accounts
