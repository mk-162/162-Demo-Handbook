---
title: Technical Audit
---

# Technical SEO Audit Checklist

Before creating new content, we must ensure the foundation is solid.

## Core Web Vitals & Speed
*   [ ] **Page Speed**: Target < 3s load time on mobile. Use [PageSpeed Insights](https://pagespeed.web.dev/).
*   [ ] **Image Optimization**: Ensure all images are compressed (WebP format preferred) and lazy-loaded.
*   [ ] **Minification**: CSS and JS files should be minified.

## Crawlability & Indexing
*   [ ] **Robots.txt**: Ensure we aren't blocking important pages.
*   [ ] **Sitemap.xml**: Must be auto-generated and submitted to Google Search Console (GSC).
*   [ ] **404 Errors**: Check GSC for broken links and set up 301 redirects.
*   [ ] **Canonical Tags**: Crucial for BigCommerce to avoid duplicate content (especially with product variants).

## Mobile Usability
*   [ ] Check "Mobile Usability" report in GSC.
*   [ ] Verify touch targets (buttons) are large enough.
*   [ ] Ensure no horizontal scrolling on phone screens.

## Structure Data (Schema)
*   [ ] **Product Schema**: Ensure Price, Availability, and Ratings are visible to Google.
*   [ ] **BreadcrumbList**: Help users and bots understand site hierarchy.
*   [ ] **Organization**: Logo and social profiles.
