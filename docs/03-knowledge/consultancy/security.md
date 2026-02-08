# Security

## The "Zero Trust" Defense Brief for CTOs

## Executive Summary

162's security architecture is built on a single principle: **your data never leaves your control.**

We host the operational logic. You hold the keys and data. We cannot see your information even if we wanted to.

## The Split-Key Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    SPLIT-KEY MODEL                          │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   162 Infrastructure          Your Environment              │
│   ──────────────────          ────────────────              │
│                                                             │
│   • MCP Server Logic          • API Keys                    │
│   • Workflow Definitions      • Customer Data               │
│   • Runbook Templates         • Environment Variables       │
│   • Code Repositories         • Access Logs                 │
│                                                             │
│   We CANNOT access your data.                               │
│   We CANNOT see your keys.                                  │
│   We CANNOT read your logs.                                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

## Security Layers

### Layer 1: Network

| Control | Implementation |
|---------|----------------|
| TLS | All connections use TLS 1.3 |
| Certificate pinning | Prevents MITM attacks |
| Network isolation | VPC per customer (Enterprise) |

### Layer 2: Authentication

| Control | Implementation |
|---------|----------------|
| API secrets | Per-customer, rotatable |
| GitHub tokens | Scoped, time-limited |
| MFA | Required for all admin access |

### Layer 3: Authorization

| Control | Implementation |
|---------|----------------|
| Role-based access | Reader, Writer, Admin roles |
| Resource scoping | Tokens limited to specific repos |
| Audit logging | All access logged and monitored |

### Layer 4: Data

| Control | Implementation |
|---------|----------------|
| Encryption at rest | AES-256 |
| Encryption in transit | TLS 1.3 |
| Key management | Customer-controlled |
| Data residency | EU-only (Enterprise) |

## Compliance

### Certifications (Roadmap)

| Certification | Status | ETA |
|---------------|--------|-----|
| SOC 2 Type I | In progress | Q2 2024 |
| SOC 2 Type II | Planned | Q4 2024 |
| ISO 27001 | Planned | 2025 |
| GDPR | Compliant | Now |

### GDPR Compliance

- **Data Processing Agreement:** Available on request
- **Right to erasure:** 30-day deletion guarantee
- **Data portability:** Export in standard formats
- **Breach notification:** Within 72 hours

## Threat Model

### What We Protect Against

| Threat | Mitigation |
|--------|------------|
| Data breach | Split-Key architecture |
| Unauthorized access | Scoped tokens + MFA |
| Insider threat | No access to customer data |
| Supply chain attack | Dependency scanning |
| DDoS | Cloudflare + rate limiting |

### What You Control

| Asset | Your Control |
|-------|--------------|
| API keys | 100% — never touch our servers |
| Customer data | 100% — stays in your environment |
| Access policies | 100% — define who can do what |
| Audit logs | 100% — stored in your systems |

## Security Checklist for CTOs

### Before Signing

- [ ] Review Data Processing Agreement
- [ ] Verify Split-Key architecture
- [ ] Check compliance certifications
- [ ] Understand incident response process

### During Implementation

- [ ] Rotate API keys (90-day policy)
- [ ] Enable MFA for all users
- [ ] Configure audit logging
- [ ] Test disaster recovery

### Ongoing

- [ ] Quarterly access review
- [ ] Annual penetration test
- [ ] Keep dependencies updated
- [ ] Monitor security advisories

## Incident Response

### Our Process

| Phase | Timeline | Action |
|-------|----------|--------|
| Detection | Immediate | Automated monitoring alerts |
| Assessment | 15 minutes | Determine scope and severity |
| Containment | 1 hour | Isolate affected systems |
| Notification | 4 hours | Inform affected customers |
| Resolution | 24 hours | Deploy fix |
| Post-mortem | 1 week | Publish incident report |

### Your Responsibilities

1. **Report suspicious activity** — security@162.consulting
2. **Rotate compromised keys** — Immediately
3. **Review access logs** — Within 24 hours
4. **Update contact info** — Keep current

## Comparison: 162 vs. Alternatives

| Feature | 162 | Generic AI Tools | Traditional Consultancies |
|---------|-----|------------------|---------------------------|
| Data leaves your environment | No | Often | Sometimes |
| You control API keys | Yes | No | Sometimes |
| Zero-Trust architecture | Yes | No | Rare |
| Audit logging | Yes | Limited | Varies |
| SOC 2 compliance | In progress | Varies | Sometimes |

## Questions for Your Security Team

1. Does the Split-Key architecture meet our requirements?
2. Can we implement our own key rotation policy?
3. What audit trails will we have access to?
4. How does this fit with our existing security stack?
5. What's the incident response process?

## Contact

- **Security inquiries:** security@162.consulting
- **Incident reporting:** incident@162.consulting
- **Compliance docs:** compliance@162.consulting

## Resources

- [Security Whitepaper](https://162.consulting/security-whitepaper)
- [Data Processing Agreement](https://162.consulting/dpa)
- [Penetration Test Reports](https://162.consulting/pentest) (NDA required)
- [Compliance Certificates](https://162.consulting/compliance) (when available)
