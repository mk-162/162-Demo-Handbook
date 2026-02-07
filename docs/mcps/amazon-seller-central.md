---
title: Amazon Seller Central
---

# Amazon Seller Central Integration

Amazon is a significant sales channel for GTSE, but API access is restricted. This guide covers available automation options.

## API Access Reality

### The Hard Truth

**Most sellers do NOT have direct API access.** Amazon's Selling Partner API (SP-API) requires:
- Professional seller account
- Developer registration approval
- Application authorization
- Compliance with Amazon's strict policies

**Approval timeline**: 2-6 weeks (if approved)

### GTSE Status

| Access Type | Status | Notes |
|-------------|--------|-------|
| Seller Central UI | ✅ Active | Manual access |
| SP-API | ⚠️ Pending/Limited | Requires application |
| Amazon MWS | ❌ Deprecated | Sunset 2024 |
| Third-party tools | ✅ Available | See options below |

## Manual Workflow (Current State)

Until SP-API is approved, use these manual processes:

### Key Reports to Pull

**Weekly:**
- Business Reports → Sales & Traffic
- Inventory → Manage FBA Inventory
- Advertising → Campaign Performance

**Monthly:**
- Payments → All Statements
- Brand Analytics (if Brand Registered)
- Returns → Returns Report

**Quarterly:**
- Seller Performance Metrics
- Account Health Dashboard

### Export Locations

```
Seller Central → Reports → Fulfillment → 
├── All Orders
├── Inventory Health
├── Stranded Inventory
└── Reserved Inventory

Seller Central → Advertising → Reports →
├── Search Term Report
├── Campaign Performance
└── Placement Report
```

## SP-API (If Approved)

### Authentication Setup

1. **Register as Developer**: Seller Central → Apps & Services → Develop Apps
2. **Create IAM User**: AWS Console with specific permissions
3. **Generate Credentials**:
   - LWA (Login with Amazon) client ID/secret
   - AWS access key/secret
   - Refresh token

### Key Endpoints

| Endpoint | Purpose | Data Freshness |
|----------|---------|----------------|
| `/orders/v0/orders` | Order retrieval | Real-time |
| `/fba/inventory/v1/summaries` | FBA stock levels | 15-30 min delay |
| `/catalog/2022-04-01/items` | Product catalog | Real-time |
| `/reports/2021-06-30/reports` | Request reports | Varies |
| `/finances/v0/financialEventGroups` | Financial data | 24-48h delay |

### Example: Get Orders

```python
import requests
from sp_api.api import Orders
from sp_api.base import Marketplaces

# With sp-api library
orders = Orders(credentials=credentials, marketplace=Marketplaces.UK)
response = orders.get_orders(CreatedAfter='2024-01-01')

for order in response.payload['Orders']:
    print(f"Order: {order['AmazonOrderId']} - {order['OrderStatus']}")
```

### Rate Limits (SP-API)

| API Section | Rate/Second | Burst |
|-------------|-------------|-------|
| Orders | 0.0167 | 20 |
| Catalog | 5 | 10 |
| Inventory | 2 | 2 |
| Reports | 0.0167 | 15 |

**Important**: These are per-selling-partner, not per-app.

## Third-Party Tools

When API access isn't viable, these tools bridge the gap:

### Recommended Options

| Tool | Use Case | Integration |
|------|----------|-------------|
| **Helium 10** | Keyword research, competitor analysis | Manual/API |
| **Jungle Scout** | Product research, sales estimates | Manual |
| **Sellics/Perpetua** | PPC automation | Direct Amazon integration |
| **SellerBoard** | Profit analytics | API (lighter approval) |
| **Zapier/Make** | Workflow automation | Various connectors |

### Data Flow Workaround

```
Amazon Seller Central
    ↓ (Manual export CSV)
Google Sheets / Airtable
    ↓ (Zapier/Make automation)
Internal Systems / Dashboards
```

### GTSE Current Stack

1. **Reporting**: Manual CSV exports → Google Sheets
2. **PPC**: [Tool TBD - evaluate Sellics vs Perpetua]
3. **Inventory**: BigCommerce → Manual sync to Amazon
4. **Analytics**: SellerBoard for profit tracking

## Automation Options

### What CAN Be Automated

| Task | Method | Complexity |
|------|--------|------------|
| Report scheduling | Amazon's built-in scheduler | Low |
| Price updates | SP-API or Repricer tools | Medium |
| Inventory sync | SP-API or channel tools | High |
| Review monitoring | Third-party tools | Low |
| PPC bid adjustments | Amazon's rules + tools | Medium |

### What Requires Manual Work

- New product listings (unless SP-API approved)
- A+ Content creation
- Responding to customer messages
- Dispute handling
- Brand Registry actions

## GTSE Amazon Workflow

### Daily Checklist

1. Check Account Health Dashboard (flags/violations)
2. Review new customer messages
3. Check FBA inventory alerts
4. Monitor PPC spend vs. target

### Weekly Checklist

1. Pull Business Reports for trending
2. Review Search Term Report → add negatives
3. Check competitor pricing on top 10 SKUs
4. Update inventory forecast

### Monthly Tasks

1. Full P&L reconciliation with SellerBoard
2. Review and update PPC strategy
3. Audit listing quality (images, bullets, A+)
4. Check for hijackers on listings

## Troubleshooting

| Issue | Cause | Solution |
|-------|-------|----------|
| API 403 Forbidden | Token expired | Refresh LWA token |
| Throttled requests | Rate limit hit | Implement exponential backoff |
| Missing data | Report not ready | Reports can take hours; poll status |
| Auth failures | Wrong marketplace | Verify marketplace endpoint |

## Official Documentation

- [SP-API Developer Guide](https://developer-docs.amazon.com/sp-api/)
- [Seller Central Help](https://sellercentral.amazon.co.uk/help)
- [Amazon MWS to SP-API Migration](https://developer-docs.amazon.com/sp-api/docs/migrating-from-amazon-mws)

## Related

- [Amazon Strategy](../amazon/index) - GTSE Amazon approach
- [Listing Optimization](../amazon/listing-optimization) - Product content
- [DSP Strategy](../amazon/dsp-strategy) - Display advertising
- [Brand Protection](../amazon/brand-protection) - Counterfeit prevention
