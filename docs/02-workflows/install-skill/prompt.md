# Prompt: Install Skill from Library

## Trigger Phrases

- "Install the [skill-name] skill"
- "Get the [skill-name] workflow from the library"
- "Download the [skill-name] skill"
- "What skills are available in the library?"

## Example Input

```
User: "Install the SEO Audit skill from the library"
```

## Expected Output

```
Found 'SEO Audit' (v1.2.0) in the 162 Library.

Category: SEO & Search
Tier: Free
Connections Required: None

Shall I install it? I can also adapt it to your brand voice.
```

## Context Required

- `01-context/subscription.md` — To check tier access
- `04-connections/` — To verify required connections exist

## Tools Required

- `list_library_skills()` — Browse available skills
- `install_skill()` — Install the skill locally
- `get_context("brand")` — For brand adaptation (optional)
