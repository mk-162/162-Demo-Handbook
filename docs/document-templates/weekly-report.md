---
title: Weekly Report
---

# Weekly Report Template

Weekly KPI dashboard for tracking Amazon, website, and operational metrics.

---

## Purpose

Use this template when:
- Preparing weekly management reports
- Tracking multi-channel e-commerce performance
- Identifying trends and issues early
- Planning actions for the coming week

---

## Template

```markdown
# Weekly Report: {{WEEK_START_DATE}} – {{WEEK_END_DATE}}

**Prepared by:** {{AUTHOR}}
**Date:** {{REPORT_DATE}}

---

## Executive Summary

{{SUMMARY_PARAGRAPH}}

**Key Highlights:**
- 📈 {{HIGHLIGHT_1}}
- 📈 {{HIGHLIGHT_2}}
- ⚠️ {{CONCERN_1}}

---

## Amazon Performance

### Sales Metrics

| Metric | This Week | Last Week | Change | Target |
|--------|-----------|-----------|--------|--------|
| Revenue | £{{AMAZON_REVENUE}} | £{{AMAZON_REVENUE_LW}} | {{AMAZON_REVENUE_CHANGE}}% | £{{AMAZON_REVENUE_TARGET}} |
| Units Sold | {{AMAZON_UNITS}} | {{AMAZON_UNITS_LW}} | {{AMAZON_UNITS_CHANGE}}% | {{AMAZON_UNITS_TARGET}} |
| Orders | {{AMAZON_ORDERS}} | {{AMAZON_ORDERS_LW}} | {{AMAZON_ORDERS_CHANGE}}% | – |
| Average Order Value | £{{AMAZON_AOV}} | £{{AMAZON_AOV_LW}} | {{AMAZON_AOV_CHANGE}}% | £{{AMAZON_AOV_TARGET}} |

### Advertising

| Metric | This Week | Last Week | Change |
|--------|-----------|-----------|--------|
| Ad Spend | £{{AD_SPEND}} | £{{AD_SPEND_LW}} | {{AD_SPEND_CHANGE}}% |
| Ad Revenue | £{{AD_REVENUE}} | £{{AD_REVENUE_LW}} | {{AD_REVENUE_CHANGE}}% |
| ACoS | {{ACOS}}% | {{ACOS_LW}}% | {{ACOS_CHANGE}}pp |
| ROAS | {{ROAS}} | {{ROAS_LW}} | {{ROAS_CHANGE}} |

### Account Health

| Metric | Current | Threshold | Status |
|--------|---------|-----------|--------|
| Order Defect Rate | {{ODR}}% | <1% | {{ODR_STATUS}} |
| Late Shipment Rate | {{LSR}}% | <4% | {{LSR_STATUS}} |
| Valid Tracking Rate | {{VTR}}% | >95% | {{VTR_STATUS}} |
| Return Rate | {{RETURN_RATE}}% | – | {{RETURN_STATUS}} |

---

## Website Performance

### Sales Metrics

| Metric | This Week | Last Week | Change | Target |
|--------|-----------|-----------|--------|--------|
| Revenue | £{{WEB_REVENUE}} | £{{WEB_REVENUE_LW}} | {{WEB_REVENUE_CHANGE}}% | £{{WEB_REVENUE_TARGET}} |
| Orders | {{WEB_ORDERS}} | {{WEB_ORDERS_LW}} | {{WEB_ORDERS_CHANGE}}% | {{WEB_ORDERS_TARGET}} |
| Average Order Value | £{{WEB_AOV}} | £{{WEB_AOV_LW}} | {{WEB_AOV_CHANGE}}% | £{{WEB_AOV_TARGET}} |
| Conversion Rate | {{WEB_CVR}}% | {{WEB_CVR_LW}}% | {{WEB_CVR_CHANGE}}pp | {{WEB_CVR_TARGET}}% |

### Traffic

| Source | Sessions | Revenue | Conv. Rate |
|--------|----------|---------|------------|
| Organic Search | {{ORGANIC_SESSIONS}} | £{{ORGANIC_REVENUE}} | {{ORGANIC_CVR}}% |
| Paid Search | {{PAID_SESSIONS}} | £{{PAID_REVENUE}} | {{PAID_CVR}}% |
| Direct | {{DIRECT_SESSIONS}} | £{{DIRECT_REVENUE}} | {{DIRECT_CVR}}% |
| Email | {{EMAIL_SESSIONS}} | £{{EMAIL_REVENUE}} | {{EMAIL_CVR}}% |
| Referral | {{REF_SESSIONS}} | £{{REF_REVENUE}} | {{REF_CVR}}% |

---

## Customer Service

| Metric | This Week | Last Week | Target | Status |
|--------|-----------|-----------|--------|--------|
| Tickets Opened | {{TICKETS_OPENED}} | {{TICKETS_OPENED_LW}} | – | – |
| Tickets Closed | {{TICKETS_CLOSED}} | {{TICKETS_CLOSED_LW}} | – | – |
| Avg Response Time | {{RESPONSE_TIME}} hrs | {{RESPONSE_TIME_LW}} hrs | <4 hrs | {{RESPONSE_STATUS}} |
| Resolution Rate | {{RESOLUTION_RATE}}% | {{RESOLUTION_RATE_LW}}% | >90% | {{RESOLUTION_STATUS}} |
| CSAT Score | {{CSAT}}/5 | {{CSAT_LW}}/5 | >4.5 | {{CSAT_STATUS}} |

### Top Issues This Week

1. {{ISSUE_1}} ({{ISSUE_1_COUNT}} tickets)
2. {{ISSUE_2}} ({{ISSUE_2_COUNT}} tickets)
3. {{ISSUE_3}} ({{ISSUE_3_COUNT}} tickets)

---

## Inventory Alerts

### Low Stock (Reorder Required)

| SKU | Product | Current Stock | Velocity/Week | Days Remaining | Action |
|-----|---------|---------------|---------------|----------------|--------|
| {{LOW_SKU_1}} | {{LOW_PRODUCT_1}} | {{LOW_STOCK_1}} | {{LOW_VELOCITY_1}} | {{LOW_DAYS_1}} | {{LOW_ACTION_1}} |
| {{LOW_SKU_2}} | {{LOW_PRODUCT_2}} | {{LOW_STOCK_2}} | {{LOW_VELOCITY_2}} | {{LOW_DAYS_2}} | {{LOW_ACTION_2}} |
| {{LOW_SKU_3}} | {{LOW_PRODUCT_3}} | {{LOW_STOCK_3}} | {{LOW_VELOCITY_3}} | {{LOW_DAYS_3}} | {{LOW_ACTION_3}} |

### Overstock (>90 Days Supply)

| SKU | Product | Current Stock | Velocity/Week | Days Supply | Notes |
|-----|---------|---------------|---------------|-------------|-------|
| {{OVER_SKU_1}} | {{OVER_PRODUCT_1}} | {{OVER_STOCK_1}} | {{OVER_VELOCITY_1}} | {{OVER_DAYS_1}} | {{OVER_NOTES_1}} |

---

## Actions for Next Week

### Carry-Forward (Not Completed)

- [ ] {{CARRYFORWARD_1}}
- [ ] {{CARRYFORWARD_2}}

### New Actions

| Priority | Action | Owner | Due |
|----------|--------|-------|-----|
| 🔴 High | {{ACTION_1}} | {{OWNER_1}} | {{DUE_1}} |
| 🟡 Medium | {{ACTION_2}} | {{OWNER_2}} | {{DUE_2}} |
| 🟡 Medium | {{ACTION_3}} | {{OWNER_3}} | {{DUE_3}} |
| 🟢 Low | {{ACTION_4}} | {{OWNER_4}} | {{DUE_4}} |

---

## Notes & Commentary

{{ADDITIONAL_NOTES}}
```

---

## Example

```markdown
# Weekly Report: 6th January – 12th January 2025

**Prepared by:** Sarah Mitchell
**Date:** 13th January 2025

---

## Executive Summary

Strong week overall with Amazon revenue up 12% on improved ad performance. Website traffic dipped slightly due to Google algorithm update but conversion rate held steady. Two stock alerts require immediate action.

**Key Highlights:**
- 📈 Amazon revenue £8,450 (+12% WoW) – best January week on record
- 📈 ACoS reduced to 18.5% from 22% through campaign optimisation
- ⚠️ CT-300-76-BK running low – reorder placed, 8 days stock remaining

---

## Amazon Performance

### Sales Metrics

| Metric | This Week | Last Week | Change | Target |
|--------|-----------|-----------|--------|--------|
| Revenue | £8,450 | £7,545 | +12.0% | £7,500 |
| Units Sold | 1,847 | 1,623 | +13.8% | 1,600 |
| Orders | 892 | 798 | +11.8% | – |
| Average Order Value | £9.47 | £9.45 | +0.2% | £9.00 |

### Advertising

| Metric | This Week | Last Week | Change |
|--------|-----------|-----------|--------|
| Ad Spend | £485 | £512 | -5.3% |
| Ad Revenue | £2,621 | £2,327 | +12.6% |
| ACoS | 18.5% | 22.0% | -3.5pp |
| ROAS | 5.4x | 4.5x | +0.9x |

### Account Health

| Metric | Current | Threshold | Status |
|--------|---------|-----------|--------|
| Order Defect Rate | 0.12% | <1% | ✅ Good |
| Late Shipment Rate | 1.2% | <4% | ✅ Good |
| Valid Tracking Rate | 99.1% | >95% | ✅ Good |
| Return Rate | 2.1% | – | ✅ Normal |

---

## Website Performance

### Sales Metrics

| Metric | This Week | Last Week | Change | Target |
|--------|-----------|-----------|--------|--------|
| Revenue | £3,280 | £3,450 | -4.9% | £3,500 |
| Orders | 187 | 198 | -5.6% | 200 |
| Average Order Value | £17.54 | £17.42 | +0.7% | £17.00 |
| Conversion Rate | 2.8% | 2.9% | -0.1pp | 3.0% |

### Traffic

| Source | Sessions | Revenue | Conv. Rate |
|--------|----------|---------|------------|
| Organic Search | 3,420 | £1,640 | 2.7% |
| Paid Search | 1,280 | £890 | 3.2% |
| Direct | 1,650 | £520 | 1.9% |
| Email | 340 | £180 | 4.1% |
| Referral | 120 | £50 | 2.5% |

---

## Customer Service

| Metric | This Week | Last Week | Target | Status |
|--------|-----------|-----------|--------|--------|
| Tickets Opened | 47 | 52 | – | – |
| Tickets Closed | 51 | 48 | – | – |
| Avg Response Time | 2.4 hrs | 3.1 hrs | <4 hrs | ✅ Good |
| Resolution Rate | 94% | 92% | >90% | ✅ Good |
| CSAT Score | 4.7/5 | 4.6/5 | >4.5 | ✅ Good |

### Top Issues This Week

1. Delivery tracking queries (12 tickets)
2. Product sizing questions (8 tickets)
3. Return requests (6 tickets)

---

## Inventory Alerts

### Low Stock (Reorder Required)

| SKU | Product | Current Stock | Velocity/Week | Days Remaining | Action |
|-----|---------|---------------|---------------|----------------|--------|
| CT-300-76-BK | Cable Ties 300x7.6mm Black | 420 | 52 | 8 days | ⚠️ Reorder placed 10/01 |
| TR-25-3M-WH | Mini Trunking 25x16mm | 85 | 12 | 7 days | ⚠️ Reorder today |
| CL-8MM-100 | Cable Clips 8mm Round | 340 | 28 | 12 days | Monitor |

### Overstock (>90 Days Supply)

| SKU | Product | Current Stock | Velocity/Week | Days Supply | Notes |
|-----|---------|---------------|---------------|-------------|-------|
| CT-150-36-WH | Cable Ties 150x3.6mm White | 2,400 | 8 | 300 days | Consider bundle promotion |

---

## Actions for Next Week

### Carry-Forward (Not Completed)

- [ ] Review Q4 return reasons for product improvement opportunities
- [ ] Update product images for top 10 Amazon listings

### New Actions

| Priority | Action | Owner | Due |
|----------|--------|-------|-----|
| 🔴 High | Place reorder for TR-25-3M-WH trunking | Mark | 14/01 |
| 🔴 High | Investigate organic traffic drop – check Google update | Sarah | 15/01 |
| 🟡 Medium | Set up bundle listing for slow-moving CT-150-36-WH | James | 17/01 |
| 🟢 Low | Draft February email campaign calendar | Sarah | 19/01 |

---

## Notes & Commentary

Google's January core update started rolling out on 8th Jan, which likely explains the 5% drop in organic traffic. Monitoring SERP positions for key terms – no major ranking changes visible yet but will reassess next week.

Amazon advertising performance significantly improved after pausing underperforming auto campaigns and reallocating budget to manual campaigns with proven keywords. Recommend continuing this approach.
```

---

## Notes

### Frequency
- Prepare weekly (recommend Monday for previous week)
- Review in weekly team meeting
- Keep for historical comparison (monthly/quarterly reviews)

### Status Indicators
- ✅ Good / On Target
- ⚠️ Warning / Needs Attention
- ❌ Critical / Off Target

### Calculating Changes
- **Percentage change**: ((This Week - Last Week) / Last Week) × 100
- **Percentage point change**: This Week % - Last Week % (use "pp" notation)

### Inventory Days Calculation
- Days Remaining = Current Stock ÷ (Weekly Velocity)
- Weekly Velocity = Units sold last 4 weeks ÷ 4

### Action Item Best Practices
- Be specific (not "improve website")
- Assign a single owner
- Set realistic due dates
- Carry forward incomplete items

### Keep It Scannable
- Use consistent formatting
- Bold or highlight changes over ±10%
- Call out anomalies in summary
- Keep commentary brief

### Data Sources Checklist
- [ ] Amazon Seller Central
- [ ] BigCommerce Analytics
- [ ] Google Analytics
- [ ] Helpdesk / Zendesk
- [ ] Inventory management system
- [ ] Google Ads / PPC platform
