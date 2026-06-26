# Service Integrations

## Required API Keys

- `TWITTER_BEARER_TOKEN`: Twitter/X API v2 profile lookup.
- `RAPIDAPI_KEY`: Optional Instagram scraper fallback provider.
- `TELEGRAM_BOT_TOKEN`: Optional Telegram bot/API integrations.

## Rate Limits

Respect each provider's published API limits. Configure retries, caching, and audit logging before production use.

## Current Behavior

The service layer exposes stable async interfaces and safe placeholders where credentials or provider-specific SDKs are not configured. This keeps local development deterministic while allowing production deployments to add compliant data providers.
