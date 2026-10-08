# LLM Multi-Model Gateway (production)

Production-grade LLM API gateway: multi-provider routing, 4-key rotation with
exponential-backoff circuit breaker, per-key sliding-window rate limiting,
SSE streaming pass-through, OpenAI↔Anthropic protocol translation, and
structured observability.

Run live in production across NVIDIA NIM, OpenAI-compatible, and third-party
aggregator backends behind a single OpenAI-compatible URL.

- `gateway_core.py` — FastAPI/uvicorn gateway (~1700 lines, battle-tested)
- `claude_compatibility.py` — OpenAI↔Anthropic message/tool-call translation
- `e2e_tool_loop_test.py` — 2-round agentic tool-loop E2E via the Anthropic surface
- `model_benchmark_results.json` — real benchmark matrix across a large model catalog (champion: glm-4-flash)

Secrets are environment-sourced (`.env`, never committed). No PII, no client keys.
