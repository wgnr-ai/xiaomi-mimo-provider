# Xiaomi MiMo Provider Plugin

Adds [Xiaomi MiMo](https://github.com/XiaoMi) as an LLM provider option in Agent Zero.

## Models

| Model | Context | Architecture | OpenRouter Route |
|-------|---------|-------------|------------------|
| MiMo V2.5 | 1M tokens | MoE 1.02T/42B active | `xiaomi/mimo-v2.5` |
| MiMo V2.5 Pro | 1M tokens | MoE 1.02T/42B active | `xiaomi/mimo-v2.5-pro` |
| MiMo V2 Omni | varies | Multimodal | `xiaomi/mimo-v2-omni` |

## Setup

1. Get an API key from Xiaomi or use via OpenRouter
2. Configure `XIAOMI_API_KEY` in Agent Zero secrets (if using direct API) or use OpenRouter routing
3. Select the appropriate provider and model in Agent Zero settings

## Architecture

- OpenAI-compatible API (`https://api.xiaomimimo.com/v1`)
- Provider ID `xiaomi` auto-maps to the `XIAOMI_API_KEY` environment variable
- Registered via `conf/model_providers.yaml` (config-only plugin, no Python code)
- Based on the Inception Labs provider plugin pattern

## Benchmarks (Artificial Analysis, April 2026)

### MiMo V2.5 Pro
- AA Intelligence Index: 54 (#1/85, tied with GPT-5.4)
- MMLU 5-shot: 89.4%
- MATH 4-shot: 86.2%
- GSM8K 8-shot: 99.6%
- GPQA Diamond: 66.7%
- Context Window: 1M tokens (1,048,576)
- Max Output: 131K tokens
- Open Source: Yes (MIT-style license)
- Architecture: MoE 1.02T total / 42B active, 384 experts, 8 per token

### Pricing (via OpenRouter)
- Input: $1.00/MTok (≤256K), $2.00/MTok (>256K)
- Output: $3.00/MTok (≤256K), $6.00/MTok (>256K)
- Cache Read: $0.20/MTok (≤256K), $0.40/MTok (>256K)
- Cache Write: Free (temporary)

## Recommended Settings
- Coding: temperature 0.3
- Research/Analysis: temperature 0.5
- Creative: temperature 0.8
- Deterministic Utility: temperature 0.1
