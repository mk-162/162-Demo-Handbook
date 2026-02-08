# GitHub API

## Scopes Required for the 'Updater' Skill

## Overview

The MCP Server uses the GitHub API to read and write content to the Handbook repository.

## Authentication

### Personal Access Token (Classic)

**Recommended for:** Individual users, small teams

**How to create:**
1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click "Generate new token (classic)"
3. Select required scopes (see below)
4. Set expiration (recommend: 90 days)
5. Copy token immediately (shown only once)

### Fine-Grained Personal Access Token

**Recommended for:** Enterprise, strict security requirements

**How to create:**
1. Go to GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens
2. Click "Generate new token"
3. Select repository access (specific repos only)
4. Set permissions (see below)
5. Set expiration

## Required Scopes

### Read-Only Operations

| Scope | Purpose | Required For |
|-------|---------|--------------|
| `repo` | Read repository content | All operations |
| `read:org` | Read organisation membership | Org-owned repos |

### Write Operations

| Scope | Purpose | Required For |
|-------|---------|--------------|
| `repo` | Write repository content | Update workflows |

### Full Scope List

```
repo          # Full control of private repositories
repo:status   # Access commit status
repo_deployment  # Access deployment status
public_repo   # Access public repositories
repo:invite   # Access repository invitations
security_events  # Read and write security events
```

## Fine-Grained Permissions

If using fine-grained tokens, these permissions are needed:

### Repository Permissions

| Permission | Access | Required |
|------------|--------|----------|
| Contents | Read and write | Yes |
| Metadata | Read | Yes |
| Pull requests | Read and write | For update workflows |

### Organisation Permissions

| Permission | Access | Required |
|------------|--------|----------|
| Members | Read | If org-owned |

## Token Security

### Best Practices

1. **Minimum scope principle**
   - Only request scopes you need
   - Use fine-grained tokens when possible

2. **Expiration**
   - Set 90-day expiration
   - Calendar reminder to rotate

3. **Storage**
   - Never commit to Git
   - Use environment variables
   - Rotate immediately if leaked

4. **Access control**
   - Limit to specific repositories
   - Review token usage regularly

### Environment Variable

```bash
# .env
GITHUB_ACCESS_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxx
```

## API Rate Limits

### Authenticated Requests

| Limit | Per Hour |
|-------|----------|
| Personal Access Token | 5,000 |
| GitHub App | 15,000 |

### Rate Limit Headers

```
X-RateLimit-Limit: 5000
X-RateLimit-Remaining: 4999
X-RateLimit-Reset: 1640995200
X-RateLimit-Used: 1
```

### Checking Your Limit

```bash
curl -H "Authorization: token $GITHUB_ACCESS_TOKEN" \
  https://api.github.com/rate_limit
```

## Common API Endpoints

### Repository Content

```bash
# Get file content
curl -H "Authorization: token $GITHUB_ACCESS_TOKEN" \
  https://api.github.com/repos/OWNER/REPO/contents/PATH

# Create/update file
curl -X PUT \
  -H "Authorization: token $GITHUB_ACCESS_TOKEN" \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/repos/OWNER/REPO/contents/PATH \
  -d '{
    "message": "commit message",
    "content": "base64encodedcontent",
    "sha": "blobsha"
  }'
```

### Pull Requests

```bash
# List PRs
curl -H "Authorization: token $GITHUB_ACCESS_TOKEN" \
  https://api.github.com/repos/OWNER/REPO/pulls

# Create PR
curl -X POST \
  -H "Authorization: token $GITHUB_ACCESS_TOKEN" \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/repos/OWNER/REPO/pulls \
  -d '{
    "title": "PR title",
    "head": "branch-name",
    "base": "main",
    "body": "PR description"
  }'
```

## Troubleshooting

### "Bad credentials"

| Cause | Solution |
|-------|----------|
| Token expired | Generate new token |
| Token revoked | Check GitHub security log |
| Wrong token format | Ensure `ghp_` prefix |

### "Not Found"

| Cause | Solution |
|-------|----------|
| Wrong owner/repo | Verify repository path |
| Token lacks access | Check token scopes |
| Private repo, no access | Request collaborator access |

### "API rate limit exceeded"

| Cause | Solution |
|-------|----------|
| Too many requests | Wait for reset |
| Inefficient code | Cache responses |
| Shared token | Use dedicated token |

## GitHub App Alternative

For production deployments, consider a GitHub App:

### Advantages

- Higher rate limits (15,000/hour)
- Better audit trail
- No personal token dependency
- Granular permissions

### Setup

1. Create app in GitHub organisation settings
2. Install app on repository
3. Generate private key
4. Use app authentication in MCP server

## Resources

- [GitHub REST API Docs](https://docs.github.com/en/rest)
- [Creating Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- [Token Scopes](https://docs.github.com/en/developers/apps/building-oauth-apps/scopes-for-oauth-apps)
- [Rate Limiting](https://docs.github.com/en/rest/overview/resources-in-the-rest-api#rate-limiting)
