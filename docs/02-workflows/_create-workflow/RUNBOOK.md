---
name: Architect New Skill
description: Create a new workflow/skill from scratch and add it to the Handbook
triggers: create a new skill, add a workflow, teach you a new task
connections: github-api, local-file-system
---

# Workflow: Architect New Skill

## Overview

This meta-skill creates new executable workflows for the 162 Handbook. Use it when you need to teach the agent a new task.

## Prerequisites

Before starting, ensure you have:
- [ ] Clear understanding of the task to be automated
- [ ] List of required tools/APIs
- [ ] Example inputs and expected outputs

## Steps

### 1. Definition

Ask the user for:
- **Trigger:** What phrase activates this workflow?
- **Action:** What steps does the agent take?
- **Outcome:** What does success look like?

Example:
```
Trigger: "Generate monthly sales report"
Action: Query Shopify, format data, email to team
Outcome: Report sent to team@company.com
```

### 2. Consistency Check

Call `get_context("system-architecture")` to verify:
- Folder naming conventions
- Required frontmatter fields
- File structure requirements

### 3. Drafting

Generate two files:

#### RUNBOOK.md

```markdown
---
name: [Human Readable Name]
description: [Short action-oriented summary]
triggers: [comma, separated, list]
connections: [list, of, tools]
---

# Workflow: [Name]

## Overview

[Brief description of what this workflow does]

## Prerequisites

- [ ] Required tool/API access
- [ ] Required context files

## Steps

### 1. [Step Name]

[Detailed instructions]

### 2. [Step Name]

[Detailed instructions]

## Success Criteria

- [ ] [Measurable outcome 1]
- [ ] [Measurable outcome 2]

## Troubleshooting

| Issue | Solution |
|-------|----------|
| [Common issue] | [How to resolve] |
```

#### prompt.md

```markdown
# Prompt: [Workflow Name]

## Trigger Phrases

- "[Primary trigger phrase]"
- "[Alternative trigger phrase]"

## Example Input

```
[Example of what the user might say]
```

## Expected Output

[Description of what the agent should produce]

## Context Required

- [List of context files to read]

## Tools Required

- [List of tools/APIs needed]
```

### 4. Commit

1. Create directory: `handbook/02-workflows/[name]/`
2. Add both files to the directory
3. Create a Pull Request with title: `Architect: Added [skill-name] workflow`

## Example: Creating a "Generate Invoice" Workflow

**User Request:**
> "Teach the agent to generate invoices from our time tracking data"

**Agent Actions:**

1. **Definition:**
   - Trigger: "Generate invoice for [client]"
   - Action: Query time tracking API, calculate totals, format invoice
   - Outcome: PDF invoice saved to /invoices/

2. **Consistency Check:**
   - Read `system-architecture.md`
   - Confirm kebab-case naming
   - Verify frontmatter requirements

3. **Drafting:**
   - Create `RUNBOOK.md` with 4-step process
   - Create `prompt.md` with trigger phrases

4. **Commit:**
   - Create `handbook/02-workflows/generate-invoice/`
   - Add files
   - Open PR

## Success Criteria

- [ ] Workflow folder created with correct naming
- [ ] RUNBOOK.md includes all required frontmatter
- [ ] prompt.md includes trigger phrases
- [ ] Pull Request opened (not direct commit)

## Related Workflows

- [Update Handbook](update-handbook/RUNBOOK.md) — Modify existing workflows
- [Website Edit](website-edit/RUNBOOK.md) — Update website content
