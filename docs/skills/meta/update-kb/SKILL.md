---
name: update-kb
title: Update Knowledge Base
description: Add, update, or extend content in the GTSE Knowledge Base. The core skill for self-extending the KB.
version: 1.0.0
authors: [Agent]
tags: [meta, documentation, git, kb-management]
---

# Update Knowledge Base

## Purpose
Enable agents to autonomously add new content to the knowledge base in the correct location, with proper formatting, and linked appropriately. This is the most critical meta-skill—it allows the KB to grow organically.

## Inputs
*   `content_type` (required): One of `playbook`, `skill`, `template`, `doc`
*   `title` (required): Human-readable title
*   `category` (required): Target category/folder
*   `content` (required): The actual content to add
*   `slug` (optional): URL-friendly filename (auto-generated from title if not provided)

## Content Type Routing

### Playbooks → `docs/playbooks/{category}/`
Step-by-step operational guides for repeatable processes.

**Format:**
```markdown
---
layout: default
title: {title}
parent: Playbooks
nav_order: {next_order}
---

# {title}

## Overview
Brief description of what this playbook achieves.

## Prerequisites
- Required access/permissions
- Tools needed

## Steps

### Step 1: {Action}
Detailed instructions...

### Step 2: {Action}
Detailed instructions...

## Success Criteria
How to know it worked.

## Troubleshooting
Common issues and fixes.
```

### Skills → `docs/skills/{category}/SKILL.md`
Executable procedures for AI agents.

**Format:**
```markdown
---
name: {slug}
title: {title}
description: {one-line description}
version: 1.0.0
authors: [Agent]
tags: [{category}, {relevant-tags}]
---

# {title}

## Purpose
Why this skill exists.

## Inputs
*   `input_name`: Description and valid values.

## Procedure
1.  **Step Name**: What to do.
2.  **Step Name**: What to do next.

## Example
> Example invocation and expected result.

## Output
What the skill produces.
```

### Templates → `docs/templates/`
Reusable document templates.

**Format:**
```markdown
---
layout: default
title: {title} Template
parent: Templates
nav_order: {next_order}
---

# {title} Template

## When to Use
Situations where this template applies.

## Template

\`\`\`markdown
{actual template content with placeholders like {{VARIABLE}}}
\`\`\`

## Variables
| Variable | Description | Example |
|----------|-------------|---------|
| {{VAR}}  | What it is  | Example |

## Example (Filled)
A completed example.
```

### Docs → `docs/{category}/`
General documentation pages.

**Format:**
```markdown
---
layout: default
title: {title}
parent: {Category Parent Title}
nav_order: {next_order}
---

# {title}

{content}
```

## Procedure

### 1. Determine Content Type & Location
Based on `content_type`, identify the target path:
- `playbook` → `docs/playbooks/{category}/{slug}.md`
- `skill` → `docs/skills/{category}/SKILL.md` (also create `index.md`)
- `template` → `docs/templates/{slug}.md`
- `doc` → `docs/{category}/{slug}.md`

### 2. Generate Slug
If `slug` not provided:
```
slug = title.lower().replace(' ', '-').replace(/[^a-z0-9-]/g, '')
```

### 3. Check for Existing Content
```bash
ls docs/{target_path}
```
If file exists, confirm with user before overwriting.

### 4. Determine nav_order
Check existing files in target directory:
```bash
grep -r "nav_order:" docs/{category}/ | sort -t: -k3 -n | tail -1
```
Use max + 1 for new content.

### 5. Create Parent Directory (if needed)
```bash
mkdir -p docs/{category}
```

### 6. Write the File
Apply the appropriate template format for the content type.

### 7. Update Parent Index
Find the parent `index.md` and add a link:
```markdown
*   **[{title}]({slug})**: {brief description}
```

### 8. Commit Changes
```bash
git add docs/{path}
git commit -m "{type}: add {title} to {category}"
```

Commit message prefixes:
- `docs:` for general documentation
- `feat:` for new skills/playbooks
- `fix:` for corrections

### 9. Push (if requested)
```bash
git push origin main
```

## Example

**User says:** "Add a B2B outreach playbook for cold calling"

**Agent executes:**
1. `content_type` = `playbook`
2. `category` = `sales`
3. `slug` = `cold-calling-playbook`
4. Creates `docs/playbooks/sales/cold-calling-playbook.md`
5. Updates `docs/playbooks/index.md` with link
6. Commits: `feat: add Cold Calling Playbook to sales`

## Output
- Path to created file
- Confirmation of index update
- Git commit hash

## Common Categories Reference

| Content | Categories |
|---------|-----------|
| playbooks | sales, marketing, operations, onboarding |
| skills | meta, research, content, automation, analysis |
| docs | amazon, website, seo, ppc, branding, operations |
