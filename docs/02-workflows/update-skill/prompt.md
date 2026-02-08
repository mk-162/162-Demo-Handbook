# Prompt: Update Skill from Library

## Trigger Phrases

- "Update the [skill-name] skill"
- "Upgrade [skill-name] workflow"
- "Fetch the latest version of [skill-name]"
- "Check for skill updates"

## Example Input

```
User: "Update the SEO Audit skill"
```

## Expected Output

```
Checking for updates to SEO Audit...

Current version: 1.0.0
Latest version: 1.2.0

Changes in v1.2.0:
- Added mobile-first indexing checks
- Improved Core Web Vitals analysis

Shall I create a Pull Request with this update?
```

## Context Required

- `.version.json` in each skill folder
- `01-context/brand.md` — To check for brand adaptations

## Tools Required

- `check_skill_updates()` — Check all skills for updates
- `update_skill()` — Update a specific skill
- GitHub API — Create branch and PR
