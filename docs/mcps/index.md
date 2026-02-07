---
title: MCPs (Tool Integrations)
---

# MCPs - Tool Integrations

MCPs (Model Context Protocols) connect AI agents to external systems. This section documents GTSE's key integrations for automated workflows.

## Why MCPs Matter

Instead of manually copy-pasting data between systems, MCPs allow:
- **Automated reporting** - Pull data from BigCommerce, GSC, and Amazon programmatically
- **Real-time decisions** - React to stock levels, search performance, or order spikes
- **Reduced human error** - Consistent data formatting and API handling

## Available Integrations

| Integration | Status | Primary Use |
|-------------|--------|-------------|
| [BigCommerce](bigcommerce) | ✅ Active | Products, orders, customers |
| [Google Search Console](google-search-console) | ✅ Active | SEO performance monitoring |
| [Amazon Seller Central](amazon-seller-central) | ⚠️ Limited | Manual + SP-API (if approved) |

## Adding New Integrations

When adding a new MCP:
1. Document authentication requirements
2. List key endpoints/capabilities
3. Include example calls
4. Note rate limits and gotchas
5. Link to official documentation

## Related Resources

- [Tools & Tech Stack](../tools/index) - Overview of all GTSE tools
- [Skills](../skills/index) - Executable workflows that use these integrations
- [Onboarding](../onboarding/index) - Access request procedures
