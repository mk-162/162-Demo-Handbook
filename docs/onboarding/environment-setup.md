---
title: Environment Setup
---

# Environment Setup

To work effectively with the GTSE ecosystem, you need to configure your local environment. This applies to developers, analysts, and AI agents operating locally.

## Prerequisites

*   **Git**: Ensure you have Git installed.
*   **Code Editor**: VS Code is recommended.
*   **Ruby**: Required if you want to preview this site locally (Jekyll).

## API Keys & Secrets

We use a `.env` file to manage secrets. **Never commit this file to the repository.**

1.  Copy the example env file:
    ```bash
    cp .env.example .env
    ```
2.  Populate the following variables:

### BigCommerce
*   `BIGCOMMERCE_STORE_HASH`: Your store's unique hash.
*   `BIGCOMMERCE_ACCESS_TOKEN`: API token with read/write permissions for Products and Orders.
*   `BIGCOMMERCE_CLIENT_ID`: Your app's client ID.

### Google Gemini
*   `GEMINI_API_KEY`: Key for generating content and images.

### GitHub
*   `GITHUB_TOKEN`: Personal Access Token (PAT) with repo scope (required for agents pushing changes).

## Connecting to Anti-Gravity

The "Anti-Gravity" system is our internal interface.
1.  Ensure you are on the company VPN (if required).
2.  Run the connection script (if applicable): `npm run connect:gravity`.

## Verification

To verify your setup, run the connection test script found in `docs/skills/setup-test/`:
```bash
python scripts/test_connection.py
```
*(Note: Ensure you have the necessary Python dependencies installed).*
