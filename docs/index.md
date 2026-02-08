# Welcome to 162

This is the **Operational Knowledge Base** for our consultancy.

It is designed to be read by:

- **Humans** — for learning and reference
- **AI Agents** — for execution of complex business workflows

## Getting Started

1. **Clone this repo**
2. **Copy `.env.example` to `.env`** and fill in your keys
3. **Connect your Agent:** Point Claude Desktop to our MCP server URL

## The 162 Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     THE BODY (Website)                      │
│              Consumer-facing Next.js Application            │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                     THE ENGINE (MCP Server)                 │
│         Secure bridge between GitHub and AI Agents          │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                     THE BRAIN (Handbook)                    │
│         Structured Knowledge Base for AI Execution          │
├─────────────────────────────────────────────────────────────┤
│  00-onboarding/  →  Getting started guides for humans       │
│  01-context/     →  Immutable facts (company, brand, etc.)  │
│  02-workflows/   →  Executable skills (runbooks)            │
│  03-knowledge/   →  Deep strategy documents                 │
│  04-connections/ →  Technical specifications                │
│  templates/      →  Reusable assets                         │
└─────────────────────────────────────────────────────────────┘
```

## Philosophy: "Boring Technology"

We reject fragile prompt engineering in favor of durable, version-controlled documentation.

- **Markdown** over proprietary formats
- **Git** over cloud-only storage
- **Structured context** over repeated prompting

## Quick Links

- [Company Profile](01-context/company.md)
- [Brand Voice](01-context/brand.md)
- [System Architecture](01-context/system-architecture.md)
- [Available Workflows](02-workflows/)
