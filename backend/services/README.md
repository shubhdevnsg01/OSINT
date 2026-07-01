# Service Integrations

## Required API Keys

- `TWITTER_BEARER_TOKEN`: Twitter/X API v2 profile lookup.
- `RAPIDAPI_KEY`: Optional Instagram scraper fallback provider.
- `TELEGRAM_BOT_TOKEN`: Optional Telegram bot/API integrations.

## Rate Limits

Respect each provider's published API limits. Configure retries, caching, and audit logging before production use.

## Current Behavior

The service layer exposes stable async interfaces and safe placeholders where credentials or provider-specific SDKs are not configured. This keeps local development deterministic while allowing production deployments to add compliant data providers.

## RapidAPI FlashAPI Integration

The FlashAPI RapidAPI provider is integrated through `backend/services/flashapi_service.py` and is called during username investigations as an enrichment provider.

Configure it with:

```powershell
$env:RAPIDAPI_KEY = "your-rapidapi-key"
$env:FLASHAPI_HOST = "flashapi1.p.rapidapi.com"
$env:FLASHAPI_BASE_URL = "https://flashapi1.p.rapidapi.com"
$env:FLASHAPI_ENDPOINT_PATH = "ig/info_username/"
```

RapidAPI calls require the `X-RapidAPI-Key` and `X-RapidAPI-Host` headers. The current FlashAPI Instagram username endpoint path is configured as `ig/info_username/`.
