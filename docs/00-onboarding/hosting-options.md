# Hosting Options

Choose the deployment model that fits your security requirements and technical capabilities.

## The Menu

| Option | Best For | Security Level | Technical Effort |
|--------|----------|----------------|------------------|
| **Managed** | Teams without DevOps | High | Minimal |
| **Self-Hosted** | Security-conscious orgs | Very High | Medium |
| **Local** | Individual developers | Maximum | Low |

---

## Option 1: Managed (Recommended)

We build and host the brain. You connect your agents.

### How It Works

```
Your Agent → Internet → 162 MCP Server → Your GitHub Repo
                ↑
         (Authenticated via API Secret)
```

### Setup

1. Sign up at [162.consulting/managed](https://162.consulting/managed)
2. Provide your GitHub repo details
3. Receive your MCP endpoint URL
4. Configure your agent to connect

### Pricing

- **Starter:** £500/month — Up to 5 workflows
- **Professional:** £1,500/month — Unlimited workflows, priority support
- **Enterprise:** Custom — Dedicated infrastructure, SLA

### Pros & Cons

**Pros:**
- Zero infrastructure management
- Automatic updates
- 99.9% uptime SLA

**Cons:**
- Data passes through 162 servers (encrypted)
- Less customization

---

## Option 2: Self-Hosted

Deploy the MCP server in your own infrastructure.

### How It Works

```
Your Agent → Your VPC → Your MCP Server → Your GitHub Repo
                ↑
         (Fully within your control)
```

### Deployment Options

#### Vercel (Easiest)

```bash
# Fork the repo
git clone https://github.com/162-consultancy/handbook.git

# Deploy to Vercel
vercel --prod
```

#### Docker

```bash
# Build the image
docker build -t 162-handbook .

# Run the container
docker run -p 3000:3000 \
  -e GITHUB_ACCESS_TOKEN=$GITHUB_ACCESS_TOKEN \
  -e MCP_API_SECRET=$MCP_API_SECRET \
  162-handbook
```

#### AWS Lambda

```bash
# Package for Lambda
npm run package:lambda

# Deploy with SAM
sam deploy --guided
```

### Pros & Cons

**Pros:**
- Complete data control
- Custom integrations
- No vendor lock-in

**Cons:**
- You manage infrastructure
- Responsible for updates

---

## Option 3: Local

Run everything on your development machine.

### How It Works

```
Your Agent → localhost:3000 → Local MCP Server → Local Git Repo
                ↑
         (No network required)
```

### Setup

```bash
# Clone the repo
git clone https://github.com/162-consultancy/handbook.git
cd handbook

# Install dependencies
npm install

# Copy environment file
cp .env.example .env
# Edit .env with your keys

# Start the development server
npm run dev
```

### Pros & Cons

**Pros:**
- Maximum security (air-gapped)
- Fast iteration
- No costs

**Cons:**
- Only works when your machine is on
- Not suitable for teams
- No automatic backups

---

## Decision Matrix

| If you... | Choose |
|-----------|--------|
| Want to get started in 5 minutes | **Managed** |
| Have a security team that reviews vendors | **Self-Hosted** |
| Are experimenting/prototyping | **Local** |
| Need SOC 2 compliance | **Self-Hosted** or **Managed Enterprise** |
| Have no DevOps resources | **Managed** |
| Want full control | **Self-Hosted** |

## Migration Path

You can migrate between options at any time:

```
Local → Self-Hosted → Managed
   ↑         ↑
   └─────────┘
   (All paths supported)
```

Your Handbook content (Markdown files) remains the same regardless of hosting option.

## Next Steps

- [Setup Guide](setup-guide.md) — Install and configure your agent
- [Troubleshooting](troubleshooting.md) — Fix common deployment issues
