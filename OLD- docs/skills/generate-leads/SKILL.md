---
name: generate-b2b-leads
title: Generate B2B Lead List
description: Use available tools/search to generate a list of prospective B2B clients.
version: 1.0.0
tags: [sales, research]
---

# Generate B2B Lead List

## Purpose
To create a targeted list of companies for ABM outreach.

## Inputs
*   `industry`: Target sector (e.g., "Solar Farm Construction").
*   `region`: Geographic focus (e.g., "Texas").
*   `role`: Target job title (e.g., "Procurement Manager").

## Procedure
1.  **Search**: Use LinkedIn or Google Boolean search.
    *   `site:linkedin.com/in/ "Procurement Manager" AND "Construction" AND "Texas"`
2.  **Filter**: Look for companies with >50 employees (likely to have budget).
3.  **Enrich**: Find the company website. Look for a "Meet the Team" page or press releases.
4.  **Output**: CSV format.
    *   Company Name, Contact Name, Role, LinkedIn URL, Website.

## Validation
*   Ensure the person is still currently employed there.
