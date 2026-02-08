# Troubleshooting

Common errors and their solutions.

## Connection Issues

### "Connection refused" or "ECONNREFUSED"

**Cause:** The MCP server is not running or is unreachable.

**Solution:**
```bash
# Check if the server is running
curl http://localhost:3000/api/mcp

# If using Managed hosting, verify the endpoint URL
# If using Local hosting, start the server:
npm run dev
```

### "Authentication failed" or "401 Unauthorized"

**Cause:** Invalid or missing `MCP_API_SECRET`.

**Solution:**
```bash
# Verify your .env file has the secret
cat .env | grep MCP_API_SECRET

# Regenerate if needed
openssl rand -hex 32
```

### "Rate limit exceeded"

**Cause:** Too many requests to the GitHub API.

**Solution:**
- Wait 60 seconds before retrying
- Check your GitHub token's rate limit:
  ```bash
  curl -H "Authorization: token $GITHUB_ACCESS_TOKEN" \
    https://api.github.com/rate_limit
  ```

---

## Agent Issues

### Hallucinations (Agent makes things up)

**Cause:** Agent is not reading context before responding.

**Solution:**
- Always prompt the agent to "check the handbook first"
- Use explicit tool calls:
  ```
  Before answering, use get_context("company") to verify facts.
  ```

### Inconsistent Output

**Cause:** Agent is not following the runbook schema.

**Solution:**
- Verify the runbook has proper frontmatter:
  ```yaml
  ---
  name: [Human Readable Name]
  description: [Short action-oriented summary]
  triggers: [comma, separated, list]
  connections: [list, of, tools]
  ---
  ```
- Ask the agent to "follow the RUNBOOK.md exactly"

### "Tool not found"

**Cause:** The MCP server doesn't expose the expected tools.

**Solution:**
```bash
# List available tools
curl http://localhost:3000/api/mcp/tools

# Verify the server is the 162 MCP server
# (Not a different MCP implementation)
```

---

## GitHub Issues

### "Repository not found"

**Cause:** Incorrect `HANDBOOK_REPO_OWNER` or `HANDBOOK_REPO_NAME`.

**Solution:**
```bash
# Verify your settings
echo $HANDBOOK_REPO_OWNER/$HANDBOOK_REPO_NAME

# Should match your GitHub URL:
# https://github.com/OWNER/REPO
```

### "Bad credentials"

**Cause:** Invalid `GITHUB_ACCESS_TOKEN`.

**Solution:**
1. Generate a new token at GitHub → Settings → Developer settings → Personal access tokens
2. Required scopes: `repo`, `read:org`
3. Update your `.env` file
4. Restart the MCP server

### "Not Found" when reading files

**Cause:** File path is incorrect or file doesn't exist.

**Solution:**
- Check the exact path in the repository
- Remember: paths are case-sensitive
- Use `list_jobs` or `list_context` to discover valid paths

---

## Workflow Issues

### "Workflow failed to execute"

**Cause:** Missing required tool or connection.

**Solution:**
1. Check the runbook's `connections:` field
2. Verify you have the required API keys in `.env`
3. Common missing keys:
   - `OPENAI_API_KEY` — for content generation
   - `VERCEL_TOKEN` — for deployments
   - `SHOPIFY_ACCESS_TOKEN` — for e-commerce

### "Pull request creation failed"

**Cause:** GitHub token lacks write permissions.

**Solution:**
- Your token needs `repo` scope (not just `public_repo`)
- For private repos, ensure the token has access

---

## Performance Issues

### Slow response times

**Cause:** Cold start or network latency.

**Solution:**
- **Managed:** First request may be slow (cold start). Subsequent requests are fast.
- **Self-Hosted:** Consider upgrading your server specs
- **Local:** Ensure your machine has sufficient RAM

### Timeouts

**Cause:** Request took longer than 30 seconds.

**Solution:**
- Break large workflows into smaller steps
- Use async patterns where possible
- Increase timeout in your agent configuration:
  ```json
  {
    "timeout": 60000
  }
  ```

---

## Getting Help

If your issue isn't listed here:

1. **Check the logs:**
   ```bash
   npm run logs
   ```

2. **Enable debug mode:**
   ```bash
   DEBUG=162:* npm run dev
   ```

3. **Contact support:**
   - Email: support@162.consulting
   - Slack: [162-community.slack.com](https://162-community.slack.com)

## Debug Checklist

When reporting an issue, include:

- [ ] Hosting option (Managed/Self-Hosted/Local)
- [ ] Error message (exact text)
- [ ] Steps to reproduce
- [ ] Your `.env` file (with secrets redacted)
- [ ] Agent being used (Claude Desktop/Cursor/other)
