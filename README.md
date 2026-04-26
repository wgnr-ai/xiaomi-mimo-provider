# Xiaomi MiMo Provider for wgnr.ai

Adds [Xiaomi MiMo](https://platform.xiaomimimo.com) models as an LLM provider option in wgnr.ai.

## Available Models

- `mimo-v2-flash` — Fast, efficient model
- `mimo-v2-pro` — Advanced reasoning
- `mimo-v2-omni` — Multimodal capabilities
- `mimo-v2.5` — Latest generation
- `mimo-v2.5-pro` — Latest generation, advanced

Models are auto-discovered from the Xiaomi API endpoint.

## Setup

1. Install this plugin via the wgnr.ai Plugin Hub
2. Get an API key at [platform.xiaomimimo.com](https://platform.xiaomimimo.com) (free tier available)
3. Set `XIAOMI_API_KEY` in your environment or enter it in Model Configuration → Advanced Settings
4. Select `xiaomi` as your provider in Model Configuration

## Custom Endpoint

If you have a dedicated API endpoint (e.g., monthly plan), enter it in the **API base URL** field under Advanced Settings in the Model Configuration UI.

## License

MIT
