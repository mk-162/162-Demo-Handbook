---
title: BigCommerce API
---

# BigCommerce API Integration

BigCommerce is GTSE's primary e-commerce platform. The API enables automation of product management, order processing, and customer data.

## Authentication Setup

### Creating API Credentials

1. Log into BigCommerce Admin Panel
2. Navigate to **Settings → API → API Accounts**
3. Click **Create API Account → Create V2/V3 API Token**
4. Set the following scopes:
   - Products: `modify`
   - Orders: `modify`
   - Customers: `modify`
   - Content: `read-only` (for CMS operations)
5. Save the credentials securely

### Required Credentials

```
Store Hash: {your-store-hash}
Client ID: {your-client-id}
Access Token: {your-access-token}
```

### Authentication Header

All requests require:
```http
X-Auth-Token: {your-access-token}
Content-Type: application/json
Accept: application/json
```

## Key Endpoints

### Products

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/v3/catalog/products` | GET | List all products |
| `/v3/catalog/products/{id}` | GET | Single product details |
| `/v3/catalog/products` | POST | Create product |
| `/v3/catalog/products/{id}` | PUT | Update product |
| `/v3/catalog/products/{id}/variants` | GET | Product variants |

### Orders

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/v2/orders` | GET | List orders |
| `/v2/orders/{id}` | GET | Order details |
| `/v2/orders/{id}/products` | GET | Order line items |
| `/v2/orders/{id}/shipments` | POST | Create shipment |

### Customers

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/v3/customers` | GET | List customers |
| `/v3/customers` | POST | Create customer |
| `/v3/customers/{id}` | PUT | Update customer |
| `/v3/customers/addresses` | GET | Customer addresses |

## Example API Calls

### Get All Products (with pagination)

```bash
curl -X GET \
  "https://api.bigcommerce.com/stores/{store_hash}/v3/catalog/products?limit=50&page=1" \
  -H "X-Auth-Token: {access_token}" \
  -H "Accept: application/json"
```

### Update Product Price

```bash
curl -X PUT \
  "https://api.bigcommerce.com/stores/{store_hash}/v3/catalog/products/{product_id}" \
  -H "X-Auth-Token: {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "price": 29.99,
    "sale_price": 24.99
  }'
```

### Get Recent Orders

```bash
curl -X GET \
  "https://api.bigcommerce.com/stores/{store_hash}/v2/orders?min_date_created=$(date -d '7 days ago' +%Y-%m-%dT%H:%M:%S%z)" \
  -H "X-Auth-Token: {access_token}" \
  -H "Accept: application/json"
```

### Create Customer

```bash
curl -X POST \
  "https://api.bigcommerce.com/stores/{store_hash}/v3/customers" \
  -H "X-Auth-Token: {access_token}" \
  -H "Content-Type: application/json" \
  -d '[{
    "email": "trade@example.com",
    "first_name": "John",
    "last_name": "Smith",
    "company": "Smith Industrial Ltd",
    "customer_group_id": 2
  }]'
```

## Rate Limits

BigCommerce implements tiered rate limiting:

| Plan | Requests/Hour | Burst Limit |
|------|---------------|-------------|
| Standard | 20,000 | 150/30s |
| Plus | 60,000 | 350/30s |
| Enterprise | Unlimited* | 1,000/30s |

*Subject to fair use policy

### Handling Rate Limits

Check response headers:
```
X-Rate-Limit-Requests-Left: 145
X-Rate-Limit-Time-Reset-Ms: 15000
```

Implement exponential backoff:
```python
import time

def api_call_with_retry(func, max_retries=3):
    for attempt in range(max_retries):
        response = func()
        if response.status_code == 429:
            wait_time = int(response.headers.get('X-Rate-Limit-Time-Reset-Ms', 30000)) / 1000
            time.sleep(wait_time)
        else:
            return response
    raise Exception("Rate limit exceeded after retries")
```

## Best Practices

### Batch Operations
- Use batch endpoints where available (e.g., `/v3/catalog/products` accepts arrays)
- Limit batch size to 10 items per request for stability

### Webhooks Over Polling
Instead of polling for order updates, configure webhooks:
- `store/order/created`
- `store/order/statusUpdated`
- `store/product/inventory/updated`

### Data Sync Strategy
1. **Full sync weekly**: Complete product/customer reconciliation
2. **Incremental hourly**: Check `date_modified` for changes
3. **Real-time webhooks**: Order and inventory events

### GTSE-Specific Notes

- **Multi-Storefront**: Use `channel_id` parameter to filter by storefront
  - UK Main: Channel 1
  - US Trade: Channel 2
- **Customer Groups**: Always assign B2B customers to group ID `2` (Trade)
- **SKU Convention**: `{CATEGORY}-{PRODUCT}-{VARIANT}` (e.g., `CT-BLK100-4.8`)

## Troubleshooting

| Error | Cause | Solution |
|-------|-------|----------|
| 401 Unauthorized | Invalid token | Regenerate API credentials |
| 404 Not Found | Wrong store hash or ID | Verify endpoint URL |
| 422 Unprocessable | Validation failure | Check required fields |
| 429 Too Many Requests | Rate limited | Implement backoff |

## Official Documentation

- [BigCommerce API Reference](https://developer.bigcommerce.com/api-reference)
- [API Best Practices](https://developer.bigcommerce.com/api-docs/getting-started/best-practices)
- [Webhooks Guide](https://developer.bigcommerce.com/api-docs/store-management/webhooks)

## Related

- [Website Strategy](../website/index) - How we use BigCommerce
- [Merchandising Rules](../website/merchandising-rules) - Product presentation
- [Operations](../operations/index) - Order fulfillment workflows
