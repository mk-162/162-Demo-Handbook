---
name: Install Skill from Library
description: Fetch a new workflow from the 162 Master Library and install it locally
triggers: install skill, get workflow from library, download skill, import workflow, check the 162 Library for
connections: github-api
---

# Workflow: Install Skill from Library

## Overview

Import vetted, optimised workflows from the 162 Master Library into your private Handbook. No file downloads or copy-pasting required.

## Prerequisites

Before starting, ensure you have:
- [ ] GitHub API access configured
- [ ] Write access to your Handbook repository

## Steps

### 1. Search the Library

1. Connect to the public repository: `162-consulting/library`
2. Fetch `catalog.json` to list available skills
3. Present the list to the user if they haven't specified a skill
4. Confirm the match if they have specified one

### 2. Check Requirements

1. Read the skill's `RUNBOOK.md` from the remote library
2. **Safety Check:** Does it require connections we don't have?
   - Check `connections:` frontmatter against available connections
   - If missing: Warn user with setup instructions

### 3. Fetch Content

1. Download `RUNBOOK.md` and `prompt.md` from remote
2. Note the version number for future update checks

### 4. Install Locally

1. Create directory: `02-workflows/{skill-id}/`
2. Write the downloaded files
3. Create `.version.json` with metadata

### 5. Brand Integration (The "162 Magic")

Ask the user: "Do you want me to adapt this skill to your Brand Voice?"

If yes:
1. Call `get_context("brand")`
2. Rewrite the 'Output' section to incorporate brand guidelines
3. Update `.version.json`: `"adapted_to_brand": true`

### 6. Completion

1. Confirm installation with trigger phrases
2. Log installation in `99-meta/change-log.md`

## Tier Enforcement

| Tier | Action |
|------|--------|
| free | Install immediately |
| pro | Check `01-context/subscription.md` for tier |
| enterprise | Validate API key |

## Success Criteria

- [ ] Skill folder created in `02-workflows/`
- [ ] RUNBOOK.md and prompt.md present
- [ ] `.version.json` created with correct metadata
- [ ] Skill appears in `list_jobs()` output

## Related Workflows

- [Update Skill](../update-skill/RUNBOOK.md)
- [Architect New Skill](../_create-workflow/RUNBOOK.md)
