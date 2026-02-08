---
name: Update Skill from Library
description: Update an existing workflow with the latest version from the 162 Master Library
triggers: update skill, upgrade workflow, fetch latest version, get new runbook
connections: github-api
---

# Workflow: Update Skill from Library

## Overview

Update a previously installed skill to the latest version from the 162 Master Library. Updates go through Pull Request for human review.

## Constants

- **Master Library Repo:** `162-consulting/library` (Public)
- **Target Directory:** `02-workflows/`

## Steps

### 1. Identify the Skill

1. Ask the user which skill they want to update
2. Verify the skill currently exists in local `02-workflows/` directory
   - If not: Suggest running the **Install Skill** workflow instead

### 2. Check Version

1. Read local `.version.json` to get current installed version
2. Fetch `catalog.json` from Master Library to get latest version
3. Compare versions:
   - If local == remote: "You already have the latest version." **Exit workflow.**
   - If local < remote: Proceed to Step 3

### 3. Fetch Latest Version

1. Connect to the **Master Library Repo** via GitHub API
2. Locate the corresponding folder in the remote `workflows/` directory
3. Read the content of `RUNBOOK.md` and `prompt.md`
4. Read `CHANGELOG.md` if available for PR description

### 4. Check for Customisations

1. Compare the remote `RUNBOOK.md` with the local version
2. If customised, ask user:
   > "I see you have customised this skill. Do you want me to overwrite your changes, or create a new 'v2' folder?"

### 5. Create Update Branch

1. Create a new branch: `update/[skill-name]-[date]`
2. Overwrite the local files with the remote content
3. Update `.version.json` with new version
4. Commit with message: "Upgraded [skill-name] to v[version] from 162 Library"

### 6. Open Pull Request

1. Open a PR merging into `main`
2. Include in PR description: version info, changelog, customisation warnings
3. Provide the PR URL to the user

## Why PR Instead of Direct Update

- Prevents breaking changes from being auto-applied
- Human reviews new requirements before accepting
- User can see exactly what changed before merging

## Success Criteria

- [ ] PR created with correct branch naming
- [ ] PR description includes version info and changelog
- [ ] `.version.json` updated in the PR

## Related Workflows

- [Install Skill](../install-skill/RUNBOOK.md)
- [Update Handbook](../update-handbook/RUNBOOK.md)
