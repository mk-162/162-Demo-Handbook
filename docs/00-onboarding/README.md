# Welcome to 162

This is the **Operational Knowledge Base** for our consultancy.

It is designed to be read by **Humans** (for learning) and **AI Agents** (for execution).

## What is 162?

162 is a premium AI consultancy that bridges the gap between generic AI capabilities and specific business operations through structured knowledge architecture.

We build **Handbooks** — version-controlled operational knowledge bases that allow AI agents to execute complex business workflows by reading structured context.

## Getting Started

### For Humans

1. **Clone this repo**
   ```bash
   git clone https://github.com/162-consultancy/handbook.git
   cd handbook
   ```

2. **Copy `.env.example` to `.env`** and fill in your keys
   ```bash
   cp .env.example .env
   ```

3. **Install dependencies**
   ```bash
   npm install
   ```

4. **Connect your Agent:** Point Claude Desktop to our MCP server URL

### For AI Agents

1. **Discover available workflows:**
   ```
   Use tool: list_jobs
   ```

2. **Read context before acting:**
   ```
   Use tool: get_context
   Parameter: topic = "company"
   ```

3. **Execute workflows:**
   ```
   Use tool: get_runbook
   Parameter: job_name = "update-handbook"
   ```

## Directory Structure

```
handbook/
├── 00-onboarding/      # Getting started guides
├── 01-context/         # Immutable facts (read-only reference)
├── 02-workflows/       # Executable skills (runbooks)
├── 03-knowledge/       # Deep strategy documents
├── 04-connections/     # Technical specifications
└── templates/          # Reusable assets
```

## Next Steps

- [Setup Guide](setup-guide.md) — Install Claude Desktop/Cursor and connect to the MCP
- [Keys Setup](keys-setup.md) — Create your local `.env` file (Split-Key security)
- [Hosting Options](hosting-options.md) — Choose your deployment model
- [Troubleshooting](troubleshooting.md) — Common errors and solutions
