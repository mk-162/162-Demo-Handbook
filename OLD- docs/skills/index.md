---
title: Skills Library
---

# Agent Skills Library

This directory contains executable skills for AI agents. Each skill is defined in a `SKILL.md` file.

## Available Skills

### Meta-Skills (Self-Extension)
*   **[Meta-Skills](meta/index)**: Skills for extending and maintaining the KB itself.
    *   [Update Knowledge Base](meta/update-kb/index) - Add content in correct locations
    *   [Find Knowledge](meta/find-knowledge/index) - Search the KB
    *   [Create Playbook](meta/create-playbook/index) - Generate step-by-step guides
    *   [Suggest Improvements](meta/suggest-improvements/index) - Audit and identify gaps

### Amazon Marketplace
*   **[Amazon Skills](amazon/index)**: Comprehensive Amazon marketplace management.
    *   [Listing Audit](amazon/listing-audit/SKILL) - Audit listings with scoring
    *   [PPC Optimizer](amazon/ppc-optimizer/SKILL) - Optimize advertising campaigns
    *   [Competitor Monitor](amazon/competitor-monitor/SKILL) - Track competitor activity
    *   [Review Response](amazon/review-response/SKILL) - Manage customer reviews

### B2B Sales & Outreach
*   **[B2B Skills](b2b/index)**: Trade customer acquisition and conversion.
    *   [Cold Outreach](b2b/cold-outreach/SKILL) - Generate prospecting messages
    *   [Outreach Sequencer](b2b/outreach-sequencer/SKILL) - Multi-touch follow-up cadences

### Marketing & Content
*   **[Marketing Skills](marketing/index)**: Content strategy and social media.
    *   [Content Strategy](marketing/content-strategy/SKILL) - B2B content planning
    *   [Social Content](marketing/social-content/SKILL) - LinkedIn-first social strategy
*   **[Draft Blog Post](draft-blog/SKILL)**: Create SEO-optimized blog content.

### Ecommerce & SEO
*   **[Ecommerce Skills](ecommerce/index)**: Store optimization and competitive intelligence.
    *   [SEO Audit](ecommerce/seo-audit/SKILL) - Comprehensive BigCommerce SEO audit
    *   [Competitor Analyzer](ecommerce/competitor-analyzer/SKILL) - UK industrial market analysis
*   **[Quick SEO Check](seo-audit/SKILL)**: 5-minute pre-publish SEO verification.

### Research & Analysis
*   **[Competitor Research](competitor-research/SKILL)**: Quick competitive intelligence.
*   **[Generate B2B Leads](generate-leads/SKILL)**: Build targeted prospect lists.

### Customer Service
*   **[Handle Complaint](handle-complaint/SKILL)**: De-escalate issues with response templates.

### Utilities
*   **[Create KB Page](create-page/SKILL)**: Add new pages to the knowledge base.
*   **[A/B Test Setup](ab-test-setup/SKILL)**: Configure website experiments.

## How to Use
Agents can read the `SKILL.md` file to understand the inputs, outputs, and procedure for a task.

## Skills by Use Case

| Task | Recommended Skill |
|------|-------------------|
| Audit an Amazon listing | [Listing Audit](amazon/listing-audit/SKILL) |
| Create outreach email | [Cold Outreach](b2b/cold-outreach/SKILL) |
| Write blog content | [Draft Blog Post](draft-blog/SKILL) |
| Check page SEO | [Quick SEO Check](seo-audit/SKILL) |
| Respond to complaint | [Handle Complaint](handle-complaint/SKILL) |
| Research competitor | [Competitor Analyzer](ecommerce/competitor-analyzer/SKILL) |
| Plan content calendar | [Content Strategy](marketing/content-strategy/SKILL) |
