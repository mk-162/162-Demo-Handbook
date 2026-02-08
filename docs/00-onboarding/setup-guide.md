# Setup Guide

This guide walks you through installing Claude Desktop (or Cursor) and connecting to the **162 Engine**.

We use a **Dual-Server Architecture**:

1. **162 Engine:** The "Librarian" (Reads context & runbooks).
2. **GitHub Server:** The "Builder" (Writes code & creates PRs).

---

## Prerequisites

- Node.js 18+ installed
- Git configured with your credentials
- A GitHub account with access to the 162 repository

---

## Step 1: Install Claude Desktop

### macOS

```bash
brew install --cask claude
```

Or download directly from [claude.ai/download](https://claude.ai/download)

### Windows

Download the installer from [claude.ai/download](https://claude.ai/download)

---

## Step 2: Configure MCP Servers

To give your agent both "Knowledge" and "Action," you need to register two separate MCP servers.

1. Open Claude Desktop
2. Go to **Settings** → **Developer** → **Edit Config**
3. Paste the following configuration (replacing the placeholders with your actual keys):

```json
{
  "mcpServers": {
    "162-engine": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/client-sse",
        "https://162.consulting/api/mcp"
      ],
      "env": {
        "MCP_API_SECRET": "your-162-secret-here"
      }
    },
    "github": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-github"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your-github-pat-here"
      }
    }
  }
}
```

### Key Reference

- **`MCP_API_SECRET`**: The random string you generated for your 162 Engine security.
- **`GITHUB_PERSONAL_ACCESS_TOKEN`**: A classic GitHub PAT with `repo` scope.

---

## Step 3: Verify Connection

Restart Claude Desktop. You should see a plug icon indicating two active servers.

### Test 1: The Brain (162 Engine)

> "List the available jobs in the handbook."
> *Expected:* It should list workflows like `website-edit`, `blog-post`, etc.

### Test 2: The Hands (GitHub Server)

> "Check the status of the repo."
> *Expected:* It should use the GitHub tool to see the current branch or commits.

---

## Step 4: Run Your First Workflow

Now, combine them. Ask the agent:

> "I want to create a new blog post about 'The Safety of Dual-Server Architecture'. Please check the brand context first, then draft the file."

**What happens next:**

1. The Agent calls **162-engine** → `get_context("brand")`.
2. The Agent calls **162-engine** → `get_runbook("blog-post")`.
3. The Agent calls **github** → `create_branch` and `push_files`.

---

## Troubleshooting

| Issue | Cause | Solution |
| --- | --- | --- |
| **"Tool not found: get_runbook"** | 162 Engine failed | Check `MCP_API_SECRET` and ensure the URL is correct. |
| **"Tool not found: create_branch"** | GitHub Server failed | Check `GITHUB_PERSONAL_ACCESS_TOKEN`. Ensure it has `repo` scope. |
| **"Connection Refused"** | API Down | If self-hosting, ensure your Next.js app is running on localhost:3000. |
