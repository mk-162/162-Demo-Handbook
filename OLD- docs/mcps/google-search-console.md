---
title: Google Search Console
---

# Google Search Console Integration

Google Search Console (GSC) is essential for monitoring GTSE's organic search performance. This guide covers API integration for automated reporting.

## Setup and Verification

### Property Verification

GTSE should have the following properties verified:
- `https://www.gtse.co.uk` (UK Main)
- `https://www.gtse.com` (US Trade)
- Domain property: `sc-domain:gtse.co.uk` (covers all subdomains)

### API Access Setup

1. **Google Cloud Project**: Create or use existing project
2. **Enable API**: Search Console API in Google Cloud Console
3. **Service Account**: Create service account for automated access
4. **Grant Access**: Add service account email to GSC property as user

```bash
# Service account email format
your-service-account@project-id.iam.gserviceaccount.com
```

### Authentication

```python
from google.oauth2 import service_account
from googleapiclient.discovery import build

SCOPES = ['https://www.googleapis.com/auth/webmasters.readonly']
credentials = service_account.Credentials.from_service_account_file(
    'service-account.json', scopes=SCOPES)

service = build('searchconsole', 'v1', credentials=credentials)
```

## Key Metrics to Monitor

### Priority Metrics

| Metric | Why It Matters | Target |
|--------|----------------|--------|
| **Clicks** | Direct traffic from Google | ↑ 10% MoM |
| **Impressions** | Visibility in search results | Trending up |
| **CTR** | Click-through rate | > 3% average |
| **Position** | Average ranking | < 20 for priority keywords |

### GTSE Focus Areas

1. **Product Category Pages**: Monitor `/cable-ties/`, `/safety-gloves/`, etc.
2. **Brand Queries**: "GTSE" branded searches (should be position 1)
3. **Competitor Gap**: Keywords where we're 11-20 (low-hanging fruit)
4. **Indexing Issues**: Pages not being indexed

## Using the API

### Search Analytics Query

```python
def get_search_analytics(site_url, start_date, end_date):
    """Fetch search performance data."""
    request = {
        'startDate': start_date,
        'endDate': end_date,
        'dimensions': ['query', 'page'],
        'rowLimit': 1000,
        'dimensionFilterGroups': [{
            'filters': [{
                'dimension': 'country',
                'expression': 'gbr'  # UK traffic only
            }]
        }]
    }
    
    response = service.searchanalytics().query(
        siteUrl=site_url, body=request).execute()
    
    return response.get('rows', [])
```

### URL Inspection

```python
def inspect_url(site_url, page_url):
    """Check indexing status of a URL."""
    request = {
        'inspectionUrl': page_url,
        'siteUrl': site_url
    }
    
    response = service.urlInspection().index().inspect(
        body=request).execute()
    
    return response['inspectionResult']
```

### Sitemaps Status

```python
def get_sitemaps(site_url):
    """List all submitted sitemaps."""
    response = service.sitemaps().list(siteUrl=site_url).execute()
    return response.get('sitemap', [])
```

## Common Queries

### Top Performing Queries

```python
# Queries with highest clicks in last 28 days
request = {
    'startDate': '2024-01-01',
    'endDate': '2024-01-28',
    'dimensions': ['query'],
    'rowLimit': 50,
    'orderBy': [{'fieldName': 'clicks', 'sortOrder': 'DESCENDING'}]
}
```

### Pages Losing Traffic

```python
# Compare two periods to find declining pages
def find_declining_pages(site_url):
    current = get_search_analytics(site_url, '2024-01-01', '2024-01-28')
    previous = get_search_analytics(site_url, '2023-12-01', '2023-12-28')
    
    # Compare and find drops > 20%
    # Implementation varies by use case
```

### Mobile vs Desktop Performance

```python
request = {
    'startDate': '2024-01-01',
    'endDate': '2024-01-28',
    'dimensions': ['device', 'query'],
    'rowLimit': 100
}
```

### Query Opportunities (Position 11-20)

```python
# Keywords where we're just off page 1
request = {
    'startDate': '2024-01-01',
    'endDate': '2024-01-28',
    'dimensions': ['query', 'page'],
    'dimensionFilterGroups': [{
        'filters': [{
            'dimension': 'position',
            'operator': 'greaterThan',
            'expression': '10'
        }, {
            'dimension': 'position',
            'operator': 'lessThan',
            'expression': '21'
        }]
    }],
    'rowLimit': 100
}
```

## Automated Reporting

### Weekly SEO Dashboard

```python
def generate_weekly_report():
    """Generate weekly SEO performance summary."""
    metrics = {
        'total_clicks': 0,
        'total_impressions': 0,
        'avg_ctr': 0,
        'avg_position': 0,
        'top_queries': [],
        'declining_pages': [],
        'opportunities': []
    }
    
    # Populate metrics...
    return metrics
```

### Alert Thresholds

Set up alerts for:
- **Traffic drop > 20%** on any priority page
- **Indexing errors** in coverage report
- **New manual actions** (critical)
- **Core Web Vitals failures** on key pages

## Rate Limits

| Quota | Limit |
|-------|-------|
| Queries per day | 2,000 |
| Queries per 100 seconds | 50 |
| URL inspections per day | 600 |

### Handling Limits

```python
import time
from functools import wraps

def rate_limited(max_per_second):
    min_interval = 1.0 / max_per_second
    def decorator(func):
        last_called = [0.0]
        @wraps(func)
        def wrapper(*args, **kwargs):
            elapsed = time.time() - last_called[0]
            wait = min_interval - elapsed
            if wait > 0:
                time.sleep(wait)
            result = func(*args, **kwargs)
            last_called[0] = time.time()
            return result
        return wrapper
    return decorator
```

## GTSE-Specific Monitoring

### Priority Pages

Monitor these pages weekly:
- `/cable-ties/` - Main category, high volume
- `/safety-gloves/` - Competitive category
- `/electrical/` - Growing category
- `/bulk-discounts/` - B2B landing page

### Competitor Keywords

Track position for:
- "cable ties bulk uk"
- "industrial safety gloves supplier"
- "trade electrical supplies"
- "wholesale workwear uk"

## Official Documentation

- [Search Console API Reference](https://developers.google.com/webmaster-tools/v1/api_reference_index)
- [Search Analytics Query](https://developers.google.com/webmaster-tools/v1/searchanalytics/query)
- [URL Inspection API](https://developers.google.com/webmaster-tools/v1/urlInspection.index/inspect)

## Related

- [SEO Strategy](../seo/index) - Overall SEO approach
- [Technical Audit](../seo/technical-audit) - Site health checks
- [SEO Audit Skill](../skills/seo-audit/SKILL) - Executable audit workflow
