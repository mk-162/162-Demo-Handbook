# Vercel

## Specs for the Next.js Deployment

## Overview

The 162 website is deployed on Vercel, the platform built by the creators of Next.js.

## Deployment Configuration

### Build Settings

| Setting | Value |
|---------|-------|
| Framework | Next.js |
| Build Command | `next build` |
| Output Directory | `.next` |
| Install Command | `npm install` |
| Node Version | 18.x |

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GITHUB_ACCESS_TOKEN` | For MCP server to read repo | Yes |
| `HANDBOOK_REPO_OWNER` | GitHub org/user name | Yes |
| `HANDBOOK_REPO_NAME` | Repository name | Yes |
| `MCP_API_SECRET` | API authentication | Yes |

### Git Integration

- **Production Branch:** `main`
- **Preview Branches:** All pull requests
- **Auto-deploy:** Enabled on push

## Project Structure

```
162-handbook/
├── app/                    # Next.js App Router
│   ├── api/mcp/           # MCP Server endpoint
│   ├── layout.tsx         # Root layout
│   ├── page.tsx           # Homepage
│   └── globals.css        # Global styles
├── components/            # React components
│   └── navbar.tsx         # Navigation
├── handbook/              # Knowledge base content
│   ├── 00-onboarding/
│   ├── 01-context/
│   ├── 02-workflows/
│   ├── 03-knowledge/
│   ├── 04-connections/
│   └── templates/
├── package.json
├── next.config.mjs
├── tailwind.config.js
└── tsconfig.json
```

## Domain Configuration

### Production

| Domain | Type |
|--------|------|
| `162.consulting` | Primary |
| `www.162.consulting` | Redirect to primary |

### Preview

| Pattern | Example |
|---------|---------|
| `[branch]-162-handbook.vercel.app` | `feature-nav-162-handbook.vercel.app` |

## Performance Optimisations

### Enabled by Default

| Feature | Status |
|---------|--------|
| Static Generation | Enabled |
| Image Optimisation | Enabled |
| Edge Network | Enabled |
| Compression | Enabled |
| Caching | 1 hour default |

### Custom Configuration

```javascript
// next.config.mjs
const nextConfig = {
  images: {
    domains: ['162.consulting'],
  },
  headers: async () => [
    {
      source: '/:path*',
      headers: [
        {
          key: 'X-Frame-Options',
          value: 'DENY',
        },
        {
          key: 'X-Content-Type-Options',
          value: 'nosniff',
        },
      ],
    },
  ],
};

export default nextConfig;
```

## Deployment Checklist

### Before First Deploy

- [ ] Environment variables configured
- [ ] Domain DNS records set
- [ ] SSL certificate provisioned
- [ ] Build passes locally

### On Every Deploy

- [ ] Preview deployment successful
- [ ] No console errors
- [ ] Links working
- [ ] Mobile responsive

## Monitoring

### Vercel Analytics

- **Web Vitals:** LCP, FID, CLS
- **Traffic:** Requests, bandwidth
- **Errors:** Function errors, 404s

### Custom Monitoring

| Metric | Tool | Alert Threshold |
|--------|------|-----------------|
| Uptime | UptimeRobot | < 99.9% |
| Performance | Vercel Analytics | LCP > 2.5s |
| Errors | Sentry | > 10/hour |

## Troubleshooting

### Build Failures

| Error | Solution |
|-------|----------|
| "Module not found" | Check import paths |
| "Type error" | Run `tsc --noEmit` locally |
| "Build timeout" | Optimise build or contact support |

### Runtime Errors

| Error | Solution |
|-------|----------|
| "Function crashed" | Check logs in Vercel dashboard |
| "Timeout" | Increase function timeout (max 60s) |
| "Memory exceeded" | Optimise or increase memory |

## Rollback

### Automatic

- Failed deployments don't replace production
- Preview deployments for all PRs

### Manual

```bash
# Via CLI
vercel --prod

# Via Dashboard
1. Go to Deployments
2. Find working deployment
3. Click "Promote to Production"
```

## Cost Estimation

| Tier | Monthly Cost | Includes |
|------|--------------|----------|
| Hobby | Free | 100GB bandwidth |
| Pro | $20 | 1TB bandwidth |
| Enterprise | Custom | Unlimited |

**Current:** Hobby (sufficient for launch)

**Upgrade when:**
- Bandwidth > 100GB/month
- Need team collaboration features
- Require SLA

## Useful Commands

```bash
# Deploy to preview
vercel

# Deploy to production
vercel --prod

# View logs
vercel logs

# List deployments
vercel list

# Remove deployment
vercel remove [deployment-url]
```

## Resources

- [Vercel Docs](https://vercel.com/docs)
- [Next.js on Vercel](https://vercel.com/docs/frameworks/nextjs)
- [Environment Variables](https://vercel.com/docs/concepts/projects/environment-variables)
