# System Architecture & Contribution Guide

**Target Audience:** AI Agents modifying this repository.

---

## 1. Directory Rules

### `01-context/` — Immutable Facts

- **Purpose:** Reference data (company, brand, services)
- **Structure:** Flat structure, one file per topic
- **Naming:** kebab-case.md (e.g., `company.md`, `brand-voice.md`)
- **Rules:**
  - Read-only for most workflows
  - Update only via `update-handbook` workflow
  - Must have clear H1 title

### `02-workflows/` — Executable Skills

- **Purpose:** Actionable runbooks for AI agents
- **Structure:** One folder per skill (kebab-case)
- **Contents:** Each folder MUST contain:
  - `RUNBOOK.md` — The instruction manual
  - `prompt.md` — The user-facing prompt template
- **Naming:** `descriptive-action-name/` (e.g., `update-handbook/`, `create-blog-post/`)

### `03-knowledge/` — Deep Strategy

- **Purpose:** Strategic documents for human reference
- **Structure:** Organised by department
- **Contents:** Markdown files with detailed analysis

### `04-connections/` — Technical Specs

- **Purpose:** API documentation and integration guides
- **Structure:** One file per integration
- **Contents:** Technical specifications, authentication details

### `templates/` — Reusable Assets

- **Purpose:** Standard formats for common outputs
- **Structure:** One file per template type
- **Contents:** Frontmatter + structure guidance

---

## 2. The Runbook Schema

Every workflow MUST have a `RUNBOOK.md` with this frontmatter:

```yaml
---
name: [Human Readable Name]
description: [Short action-oriented summary]
triggers: [comma, separated, list, of, trigger, phrases]
connections: [list, of, required, tools, and, apis]
---
```

### Example

```markdown
---
name: Update Handbook
description: Modify the knowledge base (context, workflows, or docs)
triggers: update the docs, change the handbook, fix a typo
connections: github-api
---

# Workflow: Update Handbook

1. **Fetch:** Read the file to ensure latest version
2. **Branch:** Create `update/[topic]-[date]`
3. **Commit:** Apply changes with descriptive message
4. **PR:** Open Pull Request. NEVER commit to main directly.
```

---

## 3. The Commit Protocol

### Creating a New Workflow

1. **Check if folder exists**
   ```bash
   ls handbook/02-workflows/[name]/
   ```

2. **Create folder structure**
   ```bash
   mkdir -p handbook/02-workflows/[skill-name]/
   ```

3. **Create `RUNBOOK.md`**
   - Include proper frontmatter
   - Numbered steps
   - Clear success criteria

4. **Create `prompt.md`**
   - User-facing trigger phrases
   - Example inputs

5. **Create Pull Request**
   ```
   Title: "Architect: Added [skill-name] workflow"
   Description: Brief explanation of what this workflow does
   ```

### Updating Existing Content

1. **Fetch latest version**
   - Always read before writing
   - Check for conflicts

2. **Create branch**
   ```
   Format: update/[topic]-[YYYYMMDD]
   Example: update/pricing-20240115
   ```

3. **Commit with descriptive message**
   ```
   Good: "Updated pricing table with new Enterprise tier"
   Bad: "Updated file"
   ```

4. **Open Pull Request**
   - Never commit to `main` directly
   - Request review if available

---

## 4. File Naming Conventions

| Type | Format | Example |
|------|--------|---------|
| Context files | kebab-case.md | `company.md`, `brand-voice.md` |
| Workflow folders | kebab-case/ | `update-handbook/`, `create-blog-post/` |
| Runbooks | RUNBOOK.md (uppercase) | `RUNBOOK.md` |
| Prompts | prompt.md (lowercase) | `prompt.md` |
| Templates | descriptive-name.md | `blog-post.md`, `email-update.md` |

---

## 5. Content Guidelines

### Markdown Standards

- Use ATX-style headers (`#` not `===`)
- Use fenced code blocks with language tags
- Use tables for structured data
- Use admonitions for warnings and notes

### Writing Style

- British English spelling
- Direct, concise sentences
- No jargon or hype words
- Clear hierarchy (H1 → H2 → H3)

### Frontmatter Requirements

Context files should include:
```yaml
---
description: Brief description for navigation
---
```

Workflow files MUST include:
```yaml
---
name: Human-readable name
description: What this workflow does
triggers: When to use this workflow
connections: Required tools/APIs
---
```

---

## 6. Testing Checklist

Before submitting a PR, verify:

- [ ] All files use correct naming conventions
- [ ] Frontmatter is valid YAML
- [ ] Links to other files are correct
- [ ] British English spelling used
- [ ] No forbidden words (game-changing, revolutionary, etc.)
- [ ] Code blocks have language tags
- [ ] Tables are properly formatted

---

## 7. Common Patterns

### Referencing Context

```markdown
Before executing, read the company context:
[Company Profile](../01-context/company.md)
```

### Linking Workflows

```markdown
Related workflows:
- [Update Handbook](../02-workflows/update-handbook/RUNBOOK.md)
- [Create Blog Post](../02-workflows/blog-post/RUNBOOK.md)
```

### Including Templates

```markdown
Use the [blog post template](../templates/blog-post.md) as a starting point.
```

---

## 8. Troubleshooting for Agents

### "File not found"
- Check the path is correct (case-sensitive)
- Verify the file exists in the repo
- Use `list_context` or `list_jobs` to discover valid paths

### "Permission denied"
- Ensure you're using the correct API token
- Check the token has `repo` scope
- Verify the repository owner/name is correct

### "Merge conflict"
- Fetch the latest version before editing
- Rebase your branch on main
- Resolve conflicts manually
