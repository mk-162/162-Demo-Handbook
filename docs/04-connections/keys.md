# Keys Directory

## Where to Find Keys (NOT the Keys Themselves)

## Overview

This document lists all API keys and credentials used by the 162 Handbook system. **This file does NOT contain actual keys** — it tells you where to find them.

## Key Inventory

### GitHub

| Key | Purpose | Location | Format |
|-----|---------|----------|--------|
| `GITHUB_ACCESS_TOKEN` | Read/write repo content | GitHub Settings → Developer settings → Personal access tokens | `ghp_xxxxxxxxxxxxxxxxxxxx` |

**How to obtain:**
1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click "Generate new token (classic)"
3. Select scopes: `repo`, `read:org`
4. Copy token immediately

---

### MCP Server

| Key | Purpose | Location | Format |
|-----|---------|----------|--------|
| `MCP_API_SECRET` | Authenticate agent requests | Generate locally | Random string (64 chars) |

**How to obtain:**
```bash
openssl rand -hex 32
```

---

### OpenAI (Optional)

| Key | Purpose | Location | Format |
|-----|---------|----------|--------|
| `OPENAI_API_KEY` | Content generation | OpenAI Dashboard | `sk-xxxxxxxxxxxxxxxxxxxxxxxx` |

**How to obtain:**
1. Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
2. Click "Create new secret key"
3. Copy key immediately

---

### Shopify (Optional)

| Key | Purpose | Location | Format |
|-----|---------|----------|--------|
| `SHOPIFY_ACCESS_TOKEN` | E-commerce workflows | Shopify Admin → Apps → Private apps | `shpat_xxxxxxxxxxxxxxxx` |

**How to obtain:**
1. Go to Shopify Admin
2. Settings → Apps and sales channels
3. Develop apps → Create an app
4. Configure Admin API scopes
5. Install app → Reveal token

---

### Vercel (Optional)

| Key | Purpose | Location | Format |
|-----|---------|----------|--------|
| `VERCEL_TOKEN` | Deployment workflows | Vercel Dashboard → Settings → Tokens | `vercel_token_xxxxxxxx` |

**How to obtain:**
1. Go to [vercel.com/account/tokens](https://vercel.com/account/tokens)
2. Click "Create Token"
3. Set scope and expiration
4. Copy token immediately

---

## Environment File Template

Create a file named `.env` in your project root:

```bash
# ============================================
# GITHUB (Required)
# ============================================
GITHUB_ACCESS_TOKEN=
HANDBOOK_REPO_OWNER=162-consultancy
HANDBOOK_REPO_NAME=handbook

# ============================================
# SECURITY (Required)
# ============================================
MCP_API_SECRET=

# ============================================
# AGENT TOOLS (Optional)
# ============================================
OPENAI_API_KEY=
SHOPIFY_ACCESS_TOKEN=
VERCEL_TOKEN=
```

## Key Rotation Schedule

| Key | Rotation Frequency | Reminder |
|-----|-------------------|----------|
| `GITHUB_ACCESS_TOKEN` | 90 days | Calendar event |
| `MCP_API_SECRET` | 180 days | Calendar event |
| `OPENAI_API_KEY` | 90 days | Calendar event |
| `SHOPIFY_ACCESS_TOKEN` | 180 days | Calendar event |
| `VERCEL_TOKEN` | 180 days | Calendar event |

## Key Rotation Process

### 1. Generate New Key

Create new key at the provider's dashboard.

### 2. Update Environment

```bash
# Edit .env file
nano .env

# Or update in deployment platform
vercel env add GITHUB_ACCESS_TOKEN
```

### 3. Test

```bash
# Verify new key works
npm run verify:env
```

### 4. Revoke Old Key

Go to provider dashboard and revoke the old token.

### 5. Update Documentation

If keys were shared with team, notify of rotation.

## Security Checklist

- [ ] `.env` in `.gitignore`
- [ ] Keys never committed to Git
- [ ] Keys rotated on schedule
- [ ] Minimum scopes granted
- [ ] Expiration dates set
- [ ] Team notified of rotations

## Emergency: Key Leaked

### Immediate Actions

1. **Revoke the key** (within 5 minutes)
   - Go to provider dashboard
   - Revoke immediately

2. **Generate new key**
   - Follow rotation process above

3. **Check logs**
   - Review access logs for unauthorized usage
   - Report to security@162.consulting if suspicious

4. **Notify team**
   - If shared key, inform all users
   - Update shared password manager

### Providers

| Service | Revoke URL |
|---------|------------|
| GitHub | github.com/settings/tokens |
| OpenAI | platform.openai.com/api-keys |
| Shopify | [Admin] → Apps → Develop apps |
| Vercel | vercel.com/account/tokens |

## Questions?

Contact: security@162.consulting
