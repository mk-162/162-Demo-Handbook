---
name: Update Handbook
description: Modify the knowledge base (context, workflows, or docs)
triggers: update the docs, change the handbook, fix a typo
connections: github-api
---

# Workflow: Update Handbook

## Overview

This workflow modifies existing content in the 162 Handbook. Use it for updates, corrections, and improvements to any documentation.

## Prerequisites

Before starting, ensure you have:
- [ ] The exact file path to modify
- [ ] The specific changes to make
- [ ] Understanding of the impact (who/what relies on this content)

## Steps

### 1. Fetch

Read the file to ensure you have the latest version:

```
Use tool: get_file_content
Path: handbook/[section]/[filename]
```

### 2. Branch

Create a new branch with a descriptive name:

```bash
git checkout -b update/[topic]-[YYYYMMDD]
```

Examples:
- `update/pricing-20240115`
- `fix/typo-brand-voice-20240115`
- `add/new-service-tier-20240115`

### 3. Edit

Apply the changes:

- Preserve existing formatting
- Maintain British English spelling
- Follow the style guide in [brand.md](../../01-context/brand.md)
- Update any related links if moving/renaming files

### 4. Commit

Commit with a descriptive message:

```bash
# Good
git commit -m "Updated pricing table with new Enterprise tier"
git commit -m "Fixed typo in brand voice guidelines"
git commit -m "Added security section to hosting options"

# Bad
git commit -m "Updated file"
git commit -m "Fixes"
```

### 5. Pull Request

Open a Pull Request. **NEVER commit to main directly.**

PR Title Format:
```
[Type]: [Description]

Types:
- Update: Content changes
- Fix: Corrections
- Add: New content
- Remove: Deleted content
```

Examples:
- `Update: Added Enterprise pricing tier`
- `Fix: Corrected brand voice typo`
- `Add: New security compliance section`

## Common Update Types

### Updating Context Files

When modifying `01-context/`:
- Check which workflows reference this context
- Notify if breaking changes are made
- Update version date in frontmatter if applicable

### Updating Workflows

When modifying `02-workflows/`:
- Test the workflow after changes
- Update related prompt.md if triggers change
- Document any new connections/tools

### Updating Knowledge

When modifying `03-knowledge/`:
- Ensure consistency with published strategy
- Update last-modified date
- Cross-reference with other knowledge docs

## Success Criteria

- [ ] Latest version of file was fetched before editing
- [ ] Changes are minimal and focused
- [ ] Commit message is descriptive
- [ ] Pull Request was opened (not direct commit)
- [ ] No breaking changes without notification

## Troubleshooting

| Issue | Solution |
|-------|----------|
| "File has changed" | Fetch latest and rebase your changes |
| "Merge conflict" | Resolve manually, keeping relevant changes |
| "Permission denied" | Check your GitHub token has write access |

## Related Workflows

- [Architect New Skill](_create-workflow/RUNBOOK.md) — Create new workflows
- [Website Edit](website-edit/RUNBOOK.md) — Update website content
