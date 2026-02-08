---
name: Create Blog Post
description: Research and write a new blog post
triggers: write blog post, new article, draft content
connections: google-search
---

# Workflow: Create Blog Post

## Overview

This workflow creates a new blog post following the 162 content standards. Use it for articles, thought leadership, and educational content.

## Prerequisites

Before starting, ensure you have:
- [ ] Topic or title
- [ ] Target audience
- [ ] Key points to cover

## Steps

### 1. Alignment

Call `get_context("company")` to understand:
- 162's mission and philosophy
- "Boring Technology" stance
- Target audience (CTOs, Ops Managers, Founders)

### 2. Research

Verify technical details:
- Check current best practices
- Find supporting data/statistics
- Review competitor content (for differentiation)

### 3. Draft

Write in Markdown following this structure:

```markdown
---
title: [Title]
date: [YYYY-MM-DD]
description: [Short summary for SEO/social]
---

# [Title]

## Introduction

- Hook the reader (problem or insight)
- Briefly state what they'll learn
- 2-3 paragraphs max

## Core Concept

- The main idea or argument
- Use subheadings (H2, H3) for structure
- Include code examples if technical
- Use tables for comparisons

## Technical Implementation

- How to apply this concept
- Step-by-step instructions
- Code snippets
- Best practices

## Conclusion

- Summarise key takeaways
- Call to action (what should reader do next?)
- Link to related content
```

### 4. Review

Check against brand voice:
- [ ] British English spelling
- [ ] No jargon or hype words
- [ ] Direct, concise sentences
- [ ] "Senior Peer" tone
- [ ] Clear hierarchy

### 5. Save

Save to `/posts/` with kebab-case slug:

```
/posts/why-generic-ai-fails-without-context.md
/posts/the-boring-technology-manifesto.md
/posts/how-we-cut-reporting-time-by-90-percent.md
```

## Content Guidelines

### Length

| Type | Word Count | Read Time |
|------|------------|-----------|
| Quick Tip | 300-500 | 2 min |
| Standard Post | 800-1,200 | 5 min |
| Deep Dive | 1,500-2,500 | 10 min |

### Tone

- Expert but approachable
- Honest about limitations
- Practical, not theoretical
- British English throughout

### Formatting

- Use H1 for title (in frontmatter)
- Use H2 for major sections
- Use H3 for subsections
- Use bullet points for lists
- Use tables for structured data
- Use code blocks with language tags

### SEO

- Include target keyword in first paragraph
- Use descriptive H2s
- Add meta description in frontmatter
- Link to related posts

## Example Post

```markdown
---
title: "Why Generic AI Fails Without Context"
date: 2024-01-15
description: "AI agents are only as smart as the context you give them. Here's why structured knowledge beats repeated prompting."
---

# Why Generic AI Fails Without Context

You've been there. You paste the same company description into ChatGPT for the tenth time today. Your colleague uses a different prompt for the same task. The output varies wildly.

This is the context problem — and it's why most AI implementations fail.

## The Context Gap

Generic AI doesn't know your business...

[Continue with article]
```

## Success Criteria

- [ ] Aligns with 162 philosophy
- [ ] Follows brand voice guidelines
- [ ] Proper Markdown formatting
- [ ] Saved with kebab-case slug
- [ ] Frontmatter complete

## Related Workflows

- [Social Media](social-media/RUNBOOK.md) — Distribute the post
- [Website Edit](website-edit/RUNBOOK.md) — Add to blog index
