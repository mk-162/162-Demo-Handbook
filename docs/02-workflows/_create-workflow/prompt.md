# Prompt: Architect New Skill

## Trigger Phrases

- "Create a new skill"
- "Add a workflow"
- "Teach you a new task"
- "I want to automate X"
- "Can you learn to do Y?"

## Example Input

```
I need the agent to generate monthly sales reports. 
It should query Shopify for orders, calculate totals by product, 
and email a summary to the team.
```

## Expected Output

A new workflow folder with:
1. `RUNBOOK.md` — Complete instruction manual
2. `prompt.md` — User-facing trigger template

## Context Required

- [system-architecture.md](../../01-context/system-architecture.md) — Naming conventions and schema

## Tools Required

- github-api — To commit the new workflow

## Notes

- Always use kebab-case for folder names
- Include all required frontmatter fields
- Never commit directly to main — always open a PR
