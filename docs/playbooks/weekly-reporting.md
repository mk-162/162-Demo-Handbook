---
title: Weekly Reporting
---

# Weekly Reporting Playbook

## Overview

Process for compiling weekly performance metrics across all sales channels. This report provides visibility into Amazon performance, website metrics, customer service health, and inventory status. Completed every Monday morning and distributed by noon.

**Use this when:**
- Every Monday (standard weekly cycle)
- Before leadership meetings
- When requested by management
- For month-end summaries (extended version)

## Prerequisites

- [ ] Access to Amazon Seller Central
- [ ] Access to Google Analytics
- [ ] Access to BigCommerce dashboard
- [ ] Access to customer service platform (Zendesk, Freshdesk, etc.)
- [ ] Access to inventory management system
- [ ] Reporting template (Google Sheets/Excel)

---

## Report Components

| Section | Data Source | Time Required |
|---------|-------------|---------------|
| Amazon Metrics | Seller Central | 30 min |
| Website Metrics | Google Analytics, BigCommerce | 20 min |
| Customer Service | Support platform | 15 min |
| Inventory Alerts | Inventory system | 15 min |
| Report Assembly | Template | 20 min |
| **Total** | | **~2 hours** |

---

## Step 1: Amazon Metrics

**What**: Compile sales, rankings, and advertising performance from Amazon

**How**:

### Sales & Revenue
1. Log into Amazon Seller Central
2. Navigate to Reports > Business Reports
3. Select "Sales and Traffic" by Date
4. Set date range: Previous week (Mon-Sun)
5. Export data to spreadsheet
6. Record:
   - Total ordered units
   - Total ordered product sales
   - Total orders
   - Average selling price
   - Conversion rate (Unit Session Percentage)

### Best Seller Rank (BSR)
1. Check BSR for top 10 products
2. Note category and subcategory rankings
3. Compare to previous week
4. Flag products with >20% BSR increase (declining)

### Advertising (PPC) Performance
1. Navigate to Advertising > Campaign Manager
2. Set date range to previous week
3. Export campaign performance report
4. Record at account level:
   - Total spend
   - Total sales from ads
   - ACOS (Advertising Cost of Sale)
   - ROAS (Return on Ad Spend)
   - Impressions
   - Clicks
   - CTR (Click-Through Rate)
   - CPC (Cost per Click)
5. Note top performing and underperforming campaigns

### Reviews & Ratings
1. Check for new reviews (positive and negative)
2. Record:
   - New reviews received
   - Current average rating for key products
   - Any 1-2 star reviews requiring response

**Output**: Completed Amazon section of weekly report

**Tools**: Amazon Seller Central, Business Reports, Advertising Console

---

## Step 2: Website Metrics

**What**: Compile traffic, conversion, and revenue data from BigCommerce website

**How**:

### Google Analytics Data
1. Log into Google Analytics (GA4)
2. Set date range: Previous week (Mon-Sun)
3. Compare to: Previous period
4. Navigate to Reports > Engagement > Pages and Screens
5. Record:
   - Total users
   - New users
   - Sessions
   - Bounce rate
   - Average session duration
   - Pages per session

### Traffic Sources
1. Go to Acquisition > Traffic Acquisition
2. Record sessions by channel:
   - Organic Search
   - Paid Search
   - Direct
   - Email
   - Social
   - Referral
3. Note week-over-week changes

### BigCommerce Dashboard
1. Log into BigCommerce admin
2. Navigate to Analytics > Overview
3. Set date range: Previous week
4. Record:
   - Total orders
   - Gross revenue
   - Average order value
   - Conversion rate
   - Top selling products
   - New customer vs returning

### E-commerce Conversions
1. In GA4, go to Monetization > E-commerce Purchases
2. Record:
   - E-commerce conversion rate
   - Revenue
   - Transactions
   - Average order value

**Output**: Completed website section of weekly report

**Tools**: Google Analytics, BigCommerce Admin

---

## Step 3: Customer Service Metrics

**What**: Compile support ticket performance and customer satisfaction data

**How**:

### Ticket Volume
1. Log into support platform (Zendesk/Freshdesk)
2. Navigate to Analytics/Reports
3. Set date range: Previous week
4. Record:
   - Total tickets received
   - Tickets by channel (email, phone, chat, social)
   - Tickets by category/type
   - Tickets vs previous week (% change)

### Response Performance
1. Pull response time report
2. Record:
   - First response time (average)
   - Full resolution time (average)
   - First response SLA compliance (target: 4 hours)
   - Resolution SLA compliance (target: 24 hours)

### Resolution Status
1. Check ticket status breakdown
2. Record:
   - Tickets opened this week
   - Tickets closed this week
   - Current backlog (open tickets)
   - Tickets reopened

### Customer Satisfaction
1. Pull CSAT or NPS data if available
2. Record:
   - CSAT score (target: 90%+)
   - Response rate
   - Common themes in feedback

### Notable Issues
1. Identify recurring issues
2. Flag any product quality concerns
3. Note any escalations or complaints requiring attention

**Output**: Completed customer service section of weekly report

**Tools**: Zendesk, Freshdesk, or support platform analytics

---

## Step 4: Inventory Alerts

**What**: Identify stock issues and reorder needs

**How**:

### Stock Level Review
1. Log into inventory system
2. Pull current stock levels for all products
3. Compare against:
   - Reorder point (trigger level)
   - Safety stock level
   - Weeks of cover

### Low Stock Alerts
1. Identify products below reorder point
2. Flag products with <4 weeks of stock
3. Prioritize by:
   - Sales velocity
   - Lead time from supplier
   - Strategic importance

### Overstock Identification
1. Identify products with >12 weeks of stock
2. Calculate carrying cost impact
3. Recommend clearance actions if needed

### Amazon FBA Inventory
1. Check Seller Central > Inventory > Inventory Planning
2. Record:
   - Products with excess inventory
   - Products at risk of stockout
   - Stranded inventory
   - Recommended replenishments

### Incoming Inventory
1. Note POs in transit
2. Expected arrival dates
3. Any delays or issues

**Output**: Completed inventory section with action items

**Tools**: Inventory management system, Amazon Seller Central

---

## Step 5: Report Assembly

**What**: Compile all data into final report format

**How**:

### Use Report Template
1. Open weekly report template (Google Sheets)
2. Update date range header
3. Input all collected data
4. Ensure formulas calculate correctly
5. Check data visualization (charts/graphs)

### Executive Summary
Write 3-5 bullet summary covering:
1. Total revenue (all channels)
2. Week-over-week change
3. Notable wins (top performer, milestones)
4. Concerns (issues needing attention)
5. Key action items

### Trend Analysis
1. Update rolling 4-week and 13-week trends
2. Highlight significant trend changes
3. Add context for anomalies (holidays, promotions, etc.)

### Action Items
1. List specific actions needed based on data
2. Assign owners
3. Set due dates
4. Note items carried forward from last week

**Output**: Completed weekly report ready for distribution

**Tools**: Google Sheets, report template

---

## Step 6: Report Distribution

**What**: Share report with stakeholders

**How**:

1. Review report for accuracy and completeness
2. Convert to PDF (for email) and keep live sheet link
3. Send via email to distribution list:
   - Subject: "Weekly Performance Report - [Date Range]"
   - Body: Executive summary bullets
   - Attachment: PDF report
   - Link: Live dashboard/spreadsheet
4. Post to team Slack/Teams channel
5. Archive copy in shared drive

**Output**: Report distributed to all stakeholders

**Tools**: Email, Slack/Teams, Google Drive

---

## Checklist

### Data Collection
- [ ] Amazon sales data exported
- [ ] Amazon PPC report pulled
- [ ] BSR checked for top products
- [ ] New reviews noted
- [ ] Google Analytics data pulled
- [ ] BigCommerce dashboard reviewed
- [ ] Customer service metrics compiled
- [ ] Inventory levels checked
- [ ] Low stock alerts identified

### Report Assembly
- [ ] Template updated with new data
- [ ] Charts/graphs rendering correctly
- [ ] Week-over-week comparisons calculated
- [ ] Executive summary written
- [ ] Action items documented
- [ ] Report reviewed for accuracy

### Distribution
- [ ] PDF version created
- [ ] Email sent to distribution list
- [ ] Posted to team channel
- [ ] Archived in shared drive
- [ ] Calendar reminder set for next week

---

## Templates Used

- [Weekly Report Template](/docs/templates/weekly-report)
- [KPI Dashboard Template](/docs/templates/kpi-dashboard)

---

## Related

- [Amazon Performance Tracking](/docs/amazon/performance)
- [Website Analytics Guide](/docs/website/analytics)
- [Customer Service SLAs](/docs/customer-service/slas)
- [Inventory Management](/docs/operations/inventory)

---

## Quick Reference: Key Metrics

| Area | Metric | Target | Red Flag |
|------|--------|--------|----------|
| Amazon | Conversion Rate | >10% | <7% |
| Amazon | ACOS | <25% | >35% |
| Website | Bounce Rate | <50% | >65% |
| Website | Conversion Rate | >2% | <1% |
| Service | First Response | <4 hrs | >8 hrs |
| Service | CSAT | >90% | <80% |
| Inventory | Weeks of Cover | 6-12 | <4 or >16 |

---

## Automation Opportunities

Future improvements to reduce manual effort:
- [ ] Automated data pull from Amazon API
- [ ] Google Analytics automated reports
- [ ] CRM dashboard integration
- [ ] Scheduled email distribution
- [ ] Anomaly detection alerts

---

*Last updated: February 2025*
