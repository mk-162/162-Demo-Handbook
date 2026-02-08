# Keys Setup

This guide explains how to create your local `.env` file using our Split-Key security architecture.

## Split-Key Architecture

162 uses a **Zero-Trust** security model where:

- **We host the logic** — Operational code and workflows
- **You hold the data** — API keys and customer data never leave your environment

```
┌────────────────────────────────────────────────────────────┐
│                    SPLIT-KEY MODEL                         │
├────────────────────────────────────────────────────────────┤
│                                                            │
│   162 Servers                    Your Environment          │
│   ─────────────                  ────────────────          │
│   • MCP Server Logic             • API Keys                │
│   • Workflow Definitions         • Customer Data           │
│   • Runbook Templates            • Environment Variables   │
│                                                            │
│   We CANNOT see your data even if we wanted to.            │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

## Required Keys

### GitHub (Required)

Used by the MCP Server to read the repository.

```bash
GITHUB_ACCESS_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxx
HANDBOOK_REPO_OWNER=162-consultancy
HANDBOOK_REPO_NAME=handbook
```

**How to create:**
1. Go to GitHub → Settings → Developer settings → Personal access tokens
2. Generate new token (classic)
3. Scopes needed: `repo`, `read:org`

### Security (Required)

Protects the MCP API endpoint.

```bash
MCP_API_SECRET=your-random-secret-key-here
```

**How to create:**
```bash
openssl rand -hex 32
```

### Agent Tools (Optional)

Required only if your agent needs to execute workflows locally.

```bash
# OpenAI (for content generation)
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxx

# Shopify (for e-commerce workflows)
SHOPIFY_ACCESS_TOKEN=shpat_xxxxxxxxxxxxxxxx

# Vercel (for deployment workflows)
VERCEL_TOKEN=vercel_token_xxxxxxxxxxxxxxxx
```

## Environment File Template

Create a file named `.env` in your project root:

```bash
# ============================================
# GITHUB (Required for the MCP Server to read the repo)
# ============================================
GITHUB_ACCESS_TOKEN=
HANDBOOK_REPO_OWNER=162-consultancy
HANDBOOK_REPO_NAME=handbook

# ============================================
# SECURITY (Required to protect the MCP API)
# ============================================
MCP_API_SECRET=

# ============================================
# AGENT TOOLS (Required for the Agent to execute workflows locally)
# ============================================
OPENAI_API_KEY=
SHOPIFY_ACCESS_TOKEN=
VERCEL_TOKEN=
```

## Security Best Practices

1. **Never commit `.env` to Git**
   ```bash
   echo ".env" >> .gitignore
   ```

2. **Rotate keys quarterly**
   Set a calendar reminder to regenerate tokens every 90 days.

3. **Use environment-specific keys**
   - Development: Limited-scope keys
   - Production: Full-scope keys with IP restrictions

4. **Monitor key usage**
   Check GitHub's Security → Audit log for unauthorized access.

## Verifying Your Setup

Run the verification script:

```bash
npm run verify:env
```

Or manually test:

```bash
node -e "console.log(process.env.GITHUB_ACCESS_TOKEN ? 'GitHub: OK' : 'GitHub: MISSING')"
```

## Next Steps

- [Hosting Options](hosting-options.md) — Choose where to deploy your Handbook
- [Troubleshooting](troubleshooting.md) — Fix common key-related errors
