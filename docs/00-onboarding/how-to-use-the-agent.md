# How to Use the Agent

A crash course on working with your AI agent effectively.

## Prompting vs. Runbooks

There are two ways to interact with your agent:

### 1. Free-form Prompting

Ask the agent anything, and it will try to help.

```
"What's the best way to structure a blog post?"
"Help me brainstorm marketing ideas"
"Explain our pricing model"
```

**When to use:** Exploratory questions, brainstorming, one-off tasks.

### 2. Runbook Execution

Trigger a structured workflow with a specific phrase.

```
"Write a blog post about AI in eCommerce"
"Update the pricing page"
"Create a social media thread from [URL]"
```

**When to use:** Repeatable tasks, quality-critical outputs, anything that needs consistency.

## Why Runbooks Are Better for Business Tasks

| Aspect | Free Prompting | Runbooks |
|--------|----------------|----------|
| Consistency | Varies each time | Same quality every time |
| Brand Voice | Must remind every time | Built-in |
| Error Rate | Higher | Lower |
| Training | Required | Self-documenting |

## Available Workflows

Ask the agent: "What workflows can you run?"

Or check the [02-workflows/](../02-workflows/) directory.

## Tips for Better Results

### 1. Be Specific

```
❌ "Write something about SEO"
✅ "Write a blog post about technical SEO for eCommerce sites"
```

### 2. Provide Context

```
❌ "Update the website"
✅ "Update the pricing page to reflect our new Pro tier at £500/month"
```

### 3. Use Trigger Phrases

Each workflow has specific trigger phrases. Using them ensures the agent follows the runbook.

```
✅ "Write a blog post about..." → Triggers blog-post workflow
✅ "Create a social thread from..." → Triggers social-media workflow
```

### 4. Review Before Publishing

The agent creates Pull Requests for important changes. Always review before merging.

## When the Agent Gets Stuck

1. **Check the runbook exists** — `list_jobs()`
2. **Check required connections** — Does the workflow need an API you haven't configured?
3. **Be more specific** — Vague prompts produce vague results
4. **Use the troubleshooting guide** — [troubleshooting.md](troubleshooting.md)

## The Golden Rule

> The agent is only as smart as the context you give it.

Your Handbook IS that context. Keep it updated, and your agent will keep improving.
