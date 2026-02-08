---
name: Website Content Edit
description: Edit or create new pages for the 162 Next.js site
triggers: update website, edit page, change site content
connections: local-file-system
---

# Workflow: Website Edit

## Overview

This workflow modifies content on the 162 Next.js website. Use it for homepage updates, new pages, and content changes.

## Prerequisites

Before starting, ensure you have:
- [ ] The target page/file identified
- [ ] The new content ready
- [ ] Understanding of the site's structure

## Steps

### 1. Locate

Find the target file:

| Page | File Path |
|------|-----------|
| Homepage | `app/page.tsx` |
| Layout | `app/layout.tsx` |
| Global Styles | `app/globals.css` |
| Components | `components/[name].tsx` |
| API Routes | `app/api/[route]/route.ts` |

### 2. Context

Call `get_context("brand")` to ensure "Senior Peer" voice:

- British English spelling
- Direct, concise sentences
- No jargon or hype words
- Clear hierarchy

### 3. Edit

Modify the content:

```typescript
// Example: Updating homepage headline
<section className="pt-24 pb-20 text-center">
  <h1 className="text-6xl font-bold tracking-tight mb-6">
    Your New Headline Here
  </h1>
  <p className="max-w-2xl mx-auto text-xl text-slate-600 mb-10">
    Your new subhead here.
  </p>
</section>
```

Preserve:
- Frontmatter (if present in markdown files)
- Component structure
- CSS class names
- Import statements

### 4. Preview

Remind the user that pushing triggers Vercel Preview:

```
Once you push this branch, Vercel will automatically 
create a preview deployment. Check the PR for the preview URL.
```

### 5. Commit

```bash
git add app/page.tsx
git commit -m "Updated homepage headline and subhead"
git push origin update/homepage-content-20240115
```

## Common Edits

### Updating the Homepage

File: `app/page.tsx`

Key sections:
- Hero section (headline, subhead, CTA)
- Feature sections
- Services grid
- Footer content

### Updating Navigation

File: `components/navbar.tsx`

Modify:
- Logo/text
- Navigation links
- CTA button

### Adding a New Page

1. Create file: `app/[page-name]/page.tsx`
2. Add to navigation: `components/navbar.tsx`
3. Follow existing page structure

### Updating Styles

File: `app/globals.css`

Use Tailwind classes where possible. Custom CSS only when necessary.

## Success Criteria

- [ ] File located correctly
- [ ] Brand voice maintained
- [ ] No broken imports or syntax errors
- [ ] Commit message is descriptive
- [ ] User reminded about Vercel preview

## Troubleshooting

| Issue | Solution |
|-------|----------|
| "Module not found" | Check import paths are correct |
| "Syntax error" | Verify JSX is properly closed |
| "Style not applied" | Check Tailwind class names |

## Related Workflows

- [Update Handbook](update-handbook/RUNBOOK.md) — Update documentation
- [Create Blog Post](blog-post/RUNBOOK.md) — Add blog content
