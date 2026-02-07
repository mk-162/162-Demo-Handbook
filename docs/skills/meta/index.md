---
title: Meta-Skills
---

# Meta-Skills

These skills enable agents to extend and maintain the knowledge base itself. They are the foundation for autonomous KB growth.

## Available Meta-Skills

### 📝 [Update Knowledge Base](update-kb/SKILL)
**The core skill.** Add new content to the KB in the correct location with proper formatting.
- Routes content by type (playbook, skill, template, doc)
- Applies correct templates
- Updates parent indexes
- Commits changes

### 🔍 [Find Knowledge](find-knowledge/SKILL)
Search the KB for relevant information.
- Full-text search across all docs
- Filter by category or content type
- Returns excerpts with context

### 📋 [Create Playbook](create-playbook/SKILL)
Generate comprehensive step-by-step playbooks from goals.
- Research existing content first
- Apply standard playbook template
- Include troubleshooting and success criteria

### 🔬 [Suggest Improvements](suggest-improvements/SKILL)
Audit the KB and identify gaps.
- Find thin or incomplete content
- Detect missing sections
- Recommend new playbooks/skills
- Check for outdated information

## How They Work Together

```
User: "Add a playbook for handling returns"
         │
         ▼
   ┌─────────────────┐
   │ find-knowledge  │  ← Search for existing returns content
   └────────┬────────┘
            │
            ▼
   ┌─────────────────┐
   │ create-playbook │  ← Generate the playbook content
   └────────┬────────┘
            │
            ▼
   ┌─────────────────┐
   │    update-kb    │  ← Save to correct location, commit
   └─────────────────┘
```

## Quick Reference

| Task | Skill |
|------|-------|
| "Add a new skill for X" | `update-kb` |
| "Where's our pricing info?" | `find-knowledge` |
| "Create a playbook for onboarding" | `create-playbook` → `update-kb` |
| "What's missing from the KB?" | `suggest-improvements` |
| "Document this process" | `create-playbook` or `update-kb` |

## Best Practices

1. **Always search first** - Use `find-knowledge` before creating to avoid duplicates
2. **Follow templates** - Consistency makes the KB more usable
3. **Link related content** - Cross-reference between docs
4. **Commit with context** - Use descriptive commit messages
5. **Audit regularly** - Run `suggest-improvements` monthly
