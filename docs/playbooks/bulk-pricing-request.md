---
title: Bulk Pricing Request
---

# Bulk Pricing Request Playbook

## Overview

Process for handling incoming B2B bulk quote requests from initial inquiry through close. This playbook ensures consistent qualification, accurate pricing, and professional follow-up for trade/wholesale opportunities. Typical cycle: 1-3 days for quote, 1-4 weeks to close.

**Use this when:**
- Customer requests bulk/wholesale pricing
- Trade account inquiry received
- Tender/RFQ submission required
- Existing account requests new quote

## Prerequisites

- [ ] Access to pricing calculator/margin tool
- [ ] Current product cost data
- [ ] Approved discount matrix/tiers
- [ ] Quote template
- [ ] CRM access
- [ ] Inventory visibility

---

## Step 1: Qualify the Opportunity

**What**: Determine if inquiry is legitimate and worth pursuing

**How**:

### Initial Assessment
1. Review incoming request for:
   - Company name
   - Contact name and role
   - Products of interest
   - Quantity required
   - Delivery location
   - Timeline/urgency
   - Budget mentioned

### Company Research
1. Look up company online
2. Check:
   - Legitimate business (website, LinkedIn, Companies House)
   - Industry/sector
   - Company size
   - Years in business
   - Previous orders with us (CRM check)

### Qualification Questions
If information is missing, respond with:
- What products specifically?
- What quantities?
- When do you need delivery?
- What's the delivery address?
- Is this a one-time purchase or ongoing?
- What's your decision timeline?

### Qualification Criteria
Score opportunity (0-10):
- Budget indicated: +2
- Genuine company: +2
- Realistic quantities: +2
- Clear timeline: +2
- Decision maker contact: +2

**Pursue if score ≥ 6**

**Output**: Qualified/disqualified decision, CRM record created

**Tools**: CRM, Companies House, LinkedIn, company website

---

## Step 2: Calculate Pricing Tiers

**What**: Determine appropriate discount based on quantity and customer

**How**:

### Standard Discount Matrix

| Quantity | Standard Discount | Trade Account |
|----------|-------------------|---------------|
| 10-24 units | 10% | 15% |
| 25-49 units | 15% | 20% |
| 50-99 units | 20% | 25% |
| 100-249 units | 25% | 30% |
| 250+ units | 30% | 35%+ (approval) |

### Pricing Calculation
1. Start with RRP (Recommended Retail Price)
2. Apply quantity discount from matrix
3. Factor in:
   - Customer history (repeat customer bonus)
   - Product mix (higher margin products = flexibility)
   - Competitive situation (if known)
   - Delivery costs (free over £500?)
   - Payment terms impact

### Margin Check
1. Calculate gross margin at proposed price
2. Minimum acceptable margin: 25%
3. If margin <25%, escalate for approval
4. Document margin calculation for audit

### Volume Pricing
For very large quantities (500+):
1. Calculate landed cost (product + shipping + handling)
2. Add target margin
3. Compare to market/competitor pricing
4. Present tiered options (good/better/best)

**Output**: Proposed pricing with margin analysis

**Tools**: Pricing calculator, cost spreadsheet, margin tool

---

## Step 3: Check Inventory & Lead Time

**What**: Confirm stock availability and delivery capability

**How**:

### Stock Check
1. Check current stock levels for requested products
2. Check reserved/allocated stock
3. Calculate available-to-promise (ATP)

### If Stock Available
1. Note available quantity
2. Confirm can dispatch within standard lead time (usually 2-3 days)
3. Confirm packaging/labelling requirements met

### If Partial Stock
1. Note available quantity
2. Check next delivery date for remaining
3. Decide whether to:
   - Quote partial shipment now, balance later
   - Wait for full stock before shipping
   - Source from alternative location

### If No Stock
1. Check supplier lead time
2. Calculate earliest available date
3. Confirm supplier can expedite if needed
4. Communicate realistic timeline to customer

### Special Requirements
Note any special requirements:
- Pallet delivery needed?
- Specific packaging?
- Labels or branding requirements?
- Delivery booking required?

**Output**: Stock availability confirmation, lead time estimate

**Tools**: Inventory system, supplier contacts

---

## Step 4: Prepare Proposal

**What**: Create professional quotation document

**How**:

### Quote Document Contents
1. **Header**
   - Quote number (sequential)
   - Date issued
   - Valid until (typically 14 days)

2. **Customer Details**
   - Company name
   - Contact name
   - Delivery address (if different from billing)

3. **Product Table**
   | SKU | Description | Qty | Unit Price | Line Total |
   |-----|-------------|-----|------------|------------|
   | ... | ... | ... | ... | ... |

4. **Pricing Summary**
   - Subtotal
   - Discount (if shown separately)
   - Delivery charge (or "FREE")
   - VAT
   - **Total**

5. **Terms**
   - Payment terms (e.g., 30 days from invoice)
   - Delivery timeframe
   - Quote validity
   - Minimum order value

6. **Next Steps**
   - How to order
   - Contact for questions

### Supporting Materials
Consider including:
- Product spec sheets
- Case studies/testimonials
- Trade account application (if applicable)
- Catalogue/line card

**Output**: Professional quote document (PDF)

**Tools**: Quote template, Word/Google Docs, PDF converter

---

## Step 5: Send Quote

**What**: Deliver proposal and set expectations for follow-up

**How**:

### Email Template
```
Subject: Bulk Quote for [Company Name] - Ref [Quote#]

Dear [First Name],

Thank you for your enquiry about bulk pricing for [products].

Please find attached our quotation based on the quantities discussed:

• Total: £X,XXX + VAT
• Delivery: [Free / £XX]
• Lead time: X-X working days
• Quote valid until: [Date]

To proceed, simply reply to this email or call us on [phone].

Happy to discuss if you have any questions or need adjustments to the order.

Best regards,
[Your Name]
```

### Sending Best Practices
1. Send during business hours (9 AM - 5 PM)
2. Attach quote as PDF
3. CC relevant colleagues if needed
4. BCC yourself/CRM
5. Set email tracking if available

### CRM Update
1. Log email in CRM
2. Update opportunity stage to "Quote Sent"
3. Set follow-up task for Day 3
4. Add quote value to pipeline

**Output**: Quote delivered, CRM updated, follow-up scheduled

**Tools**: Email, CRM, calendar

---

## Step 6: Follow-Up Sequence

**What**: Systematic follow-up to maximize close rate

**How**:

### Follow-Up Timeline

| Day | Action | Method |
|-----|--------|--------|
| 0 | Quote sent | Email |
| 3 | Check received | Email/Call |
| 7 | Value reinforcement | Email |
| 14 | Quote expiry reminder | Email |
| 21 | New offer/incentive | Email/Call |
| 30 | Final attempt | Call |

### Day 3: Check-In
```
Subject: RE: Bulk Quote - Quick Check-In

Hi [Name],

Just checking you received the quote I sent across. Happy to jump on a quick call if you'd like to discuss any details.

Is there anything I can help with?

[Your Name]
```

### Day 7: Value Add
```
Subject: RE: Bulk Quote - Quick Question

Hi [Name],

Following up on the quote - have you had a chance to review?

I wanted to mention that [value add: we can hold stock, offer extended terms, include samples, etc.].

Let me know if you have any questions.

[Your Name]
```

### Day 14: Urgency
```
Subject: Quote Expiry Reminder - [Quote#]

Hi [Name],

Quick note that your quote expires on [date]. 

Should I extend it, or are you ready to proceed?

Happy to help with anything.

[Your Name]
```

### Day 21+: Reassess
- Call to understand blockers
- Offer alternative products/quantities
- Negotiate if needed
- Determine if opportunity is dead

**Output**: Systematic follow-up complete, opportunity progressed or closed

**Tools**: Email, phone, CRM tasks

---

## Step 7: Close or Document Loss

**What**: Finalize outcome and capture learnings

**How**:

### If Won
1. Convert quote to order
2. Process payment or set up invoice terms
3. Update CRM: Opportunity → Closed Won
4. Hand off to operations for fulfilment
5. Send order confirmation
6. Set up for trade account (if ongoing relationship)
7. Schedule post-delivery check-in

### If Lost
1. Try to understand why:
   - Price too high?
   - Lead time too long?
   - Went with competitor?
   - Project cancelled?
   - Internal budget issue?
2. Update CRM: Opportunity → Closed Lost
3. Record loss reason
4. Set reminder for future follow-up (3-6 months)
5. Add to nurture campaign if appropriate

### Win/Loss Analysis
Track for monthly review:
- Win rate by product category
- Average deal size
- Time to close
- Common loss reasons
- Competitive losses

**Output**: Closed opportunity with documented outcome

**Tools**: CRM, order management system

---

## Checklist

### Qualification
- [ ] Inquiry received and logged
- [ ] Company research completed
- [ ] Missing information requested
- [ ] Qualification score calculated
- [ ] CRM opportunity created

### Pricing
- [ ] Quantities confirmed
- [ ] Discount tier applied
- [ ] Margin calculated and acceptable
- [ ] Special terms noted
- [ ] Approval obtained (if needed)

### Inventory
- [ ] Stock availability checked
- [ ] Lead time confirmed
- [ ] Special requirements noted
- [ ] Supplier notified (if needed)

### Proposal
- [ ] Quote document prepared
- [ ] Pricing accurate
- [ ] Terms clearly stated
- [ ] Supporting materials attached

### Delivery
- [ ] Quote sent during business hours
- [ ] CRM updated with stage change
- [ ] Follow-up tasks scheduled
- [ ] Email tracking enabled

### Follow-Up
- [ ] Day 3 follow-up completed
- [ ] Day 7 follow-up completed
- [ ] Day 14 reminder sent
- [ ] Final follow-up call made

### Close
- [ ] Outcome documented (won/lost)
- [ ] CRM updated with reason
- [ ] Order processed (if won)
- [ ] Future follow-up scheduled (if lost)

---

## Templates Used

- [Bulk Quote Template](/docs/templates/bulk-quote)
- [Quote Email Template](/docs/templates/quote-email)
- [Trade Account Application](/docs/templates/trade-account)
- [Follow-Up Email Sequence](/docs/templates/followup-sequence)

---

## Related

- [B2B Outreach Campaign Playbook](b2b-outreach-campaign)
- [Pricing Strategy Guide](/docs/sales/pricing)
- [Trade Account Setup](/docs/sales/trade-accounts)
- [CRM Best Practices](/docs/tools/crm)

---

## Response Time SLAs

| Action | Target Time | Maximum |
|--------|-------------|---------|
| Acknowledge inquiry | 2 hours | Same day |
| Send quote | Same day | 24 hours |
| Answer questions | 2 hours | 4 hours |
| Follow-up | As scheduled | +1 day |

---

## Escalation

Escalate to management if:
- Quantity exceeds 500 units
- Discount requested exceeds matrix
- Custom/OEM request
- Competitor match request
- Credit terms >30 days
- International delivery
- Customer complaint

---

*Last updated: February 2025*
