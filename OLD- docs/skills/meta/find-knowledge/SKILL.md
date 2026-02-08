---
name: find-knowledge
title: Find Knowledge
description: Search the GTSE Knowledge Base for relevant information, returning file paths and excerpts.
version: 1.0.0
authors: [Agent]
tags: [meta, search, research, kb-management]
---

# Find Knowledge

## Purpose
Quickly locate relevant documentation, playbooks, skills, or templates within the knowledge base. Essential for answering questions, avoiding duplicate content, and building on existing knowledge.

## Inputs
*   `query` (required): Search terms or question
*   `category` (optional): Limit search to specific folder (e.g., `sales`, `seo`, `skills`)
*   `content_type` (optional): Filter by type (`playbook`, `skill`, `doc`, `template`)
*   `max_results` (optional): Maximum number of results (default: 5)

## Procedure

### 1. Prepare Search
Navigate to the KB root:
```bash
cd /path/to/GTSE-AI-HUB/docs
```

### 2. Build Search Scope
Determine search path based on inputs:
- If `category` specified: `docs/{category}/`
- If `content_type` is `skill`: `docs/skills/`
- If `content_type` is `playbook`: `docs/playbooks/` or search for `*playbook*`
- If `content_type` is `template`: `docs/templates/`
- Otherwise: `docs/`

### 3. Execute Search
Primary search using grep (case-insensitive, with context):
```bash
grep -rnil --include="*.md" "{query}" {search_path} | head -{max_results}
```

For multi-word queries, search each term:
```bash
grep -rnil --include="*.md" -e "term1" -e "term2" {search_path}
```

### 4. Get Context for Each Match
For each matching file, extract relevant excerpt:
```bash
grep -B2 -A5 -i "{query}" {file_path}
```

### 5. Extract Metadata
For each result, parse frontmatter:
```bash
head -20 {file_path} | grep -E "^(title|description|parent|tags):"
```

### 6. Rank Results
Prioritize by:
1. Title matches (highest)
2. Frontmatter/description matches
3. Heading matches (## or ###)
4. Body content matches (lowest)

### 7. Format Output
Compile results into structured response.

## Example

**Query:** "How do we handle customer complaints?"

**Search execution:**
```bash
grep -rnil --include="*.md" -e "complaint" -e "customer" docs/
```

**Output:**
```
## Search Results for "customer complaints"

### 1. Customer Complaint Handling
**File:** `docs/skills/handle-complaint/SKILL.md`
**Type:** Skill
**Excerpt:**
> ## Purpose
> To resolve customer complaints efficiently while maintaining brand reputation...

### 2. Customer Service Scripts
**File:** `docs/customer-service/scripts.md`
**Type:** Doc
**Excerpt:**
> ### Handling Complaints
> 1. Acknowledge the issue
> 2. Apologize sincerely...

### 3. Returns & RMA Process
**File:** `docs/operations/returns-rma.md`
**Type:** Doc
**Excerpt:**
> When a customer is unhappy with their order...

---
*Found 3 relevant documents*
```

## Output Format

```markdown
## Search Results for "{query}"

### {n}. {title}
**File:** `{relative_path}`
**Type:** {content_type}
**Tags:** {tags if available}
**Excerpt:**
> {2-5 lines of relevant content}

---
*Found {count} relevant documents*
```

## Advanced Search Patterns

### Find all playbooks
```bash
find docs -name "*playbook*" -o -path "*/playbooks/*"
```

### Find skills by tag
```bash
grep -rl "tags:.*\[.*{tag}.*\]" docs/skills/
```

### Find recently modified
```bash
find docs -name "*.md" -mtime -7 -type f
```

### Find incomplete docs (TODO markers)
```bash
grep -rn "TODO\|FIXME\|WIP\|TBD" docs/
```

### Find by author
```bash
grep -rl "authors:.*{name}" docs/
```

## No Results Handling
If no results found:
1. Suggest related categories to explore
2. Recommend creating new content via `update-kb` skill
3. Offer to search with broader terms

## Tips
- Use specific terms over generic ones
- Check both singular and plural forms
- Search for acronyms AND full terms (e.g., "PPC" and "pay per click")
- Look in `skills/` for "how to" questions
- Look in `playbooks/` for process questions
