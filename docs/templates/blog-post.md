# Blog Post Template

## Standard Frontmatter Structure for Articles

## Template

```markdown
---
title: [Title]
date: [YYYY-MM-DD]
description: [Short summary for SEO and social sharing]
author: [Author Name]
tags: [tag1, tag2, tag3]
---

# [Title]

## Introduction

[Hook the reader with a problem, insight, or question. 2-3 paragraphs max.]

## Core Concept

[The main idea or argument. Use subheadings for structure.]

### [Subheading 1]

[Content]

### [Subheading 2]

[Content]

## Technical Implementation

[How to apply this concept. Step-by-step instructions, code snippets, best practices.]

```typescript
// Example code block
const example = "Use fenced code blocks with language tags";
```

## Conclusion

[Summarise key takeaways. Call to action — what should the reader do next?]

---

[Link to related content]
```

## Frontmatter Fields

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| `title` | Yes | Article title | "Why Generic AI Fails" |
| `date` | Yes | Publication date | "2024-01-15" |
| `description` | Yes | SEO/social summary | "AI agents are only as smart..." |
| `author` | No | Author name | "Jane Smith" |
| `tags` | No | Related topics | `["ai", "workflows", "context"]` |

## Content Guidelines

### Length

| Type | Word Count | Read Time |
|------|------------|-----------|
| Quick Tip | 300-500 | 2 min |
| Standard Post | 800-1,200 | 5 min |
| Deep Dive | 1,500-2,500 | 10 min |

### Structure

1. **Introduction** (10%)
   - Hook
   - Problem statement
   - What reader will learn

2. **Core Concept** (50%)
   - Main argument
   - Supporting evidence
   - Examples

3. **Implementation** (30%)
   - How to apply
   - Code/examples
   - Best practices

4. **Conclusion** (10%)
   - Summary
   - Call to action
   - Related links

### Formatting

- Use H1 for title (in frontmatter)
- Use H2 for major sections
- Use H3 for subsections
- Use bullet points for lists
- Use tables for comparisons
- Use code blocks with language tags

## Example

```markdown
---
title: "Why Generic AI Fails Without Context"
date: 2024-01-15
description: "AI agents are only as smart as the context you give them. Here's why structured knowledge beats repeated prompting."
author: "162 Team"
tags: ["ai", "context", "workflows"]
---

# Why Generic AI Fails Without Context

You've been there. You paste the same company description into ChatGPT for the tenth time today. Your colleague uses a different prompt for the same task. The output varies wildly.

This is the context problem — and it's why most AI implementations fail.

## The Context Gap

Generic AI doesn't know your business. It doesn't understand your brand voice, your pricing structure, or your target customers. Every interaction starts from zero.

### The Cost of Repetition

| Task | Time Wasted (Daily) | Annual Cost |
|------|---------------------|-------------|
| Pasting context | 30 min | £3,000 |
| Fixing inconsistencies | 45 min | £4,500 |
| Re-explaining requirements | 20 min | £2,000 |

## The Solution: Structured Context

Instead of repeating yourself, codify your knowledge:

1. **Company context** — Mission, values, positioning
2. **Brand voice** — Tone, style, forbidden words
3. **Workflows** — Step-by-step processes
4. **Templates** — Reusable formats

```typescript
// Example: Reading context before generating
const context = await getContext("company");
const output = await generate({ prompt, context });
```

## Conclusion

Stop prompting. Start operating.

When your AI has structured context, it becomes a team member — not a toy.

[Read more about the 162 Methodology →](/methodology)
```

## Checklist

Before publishing:

- [ ] Frontmatter complete
- [ ] Title is descriptive
- [ ] Description under 160 characters
- [ ] Introduction hooks the reader
- [ ] British English spelling
- [ ] No jargon or hype words
- [ ] Code blocks have language tags
- [ ] Links work
- [ ] Call to action included
