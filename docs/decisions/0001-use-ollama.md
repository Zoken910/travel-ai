# 0001 — Run the LLM locally with Ollama

Date: 2026-10-29 · Status: accepted

## Context

The planner needs an LLM to parse free-text preferences into structured requests and to write
itineraries from scored candidates. Traveler profiles (budget, dates, accessibility, diet) are
personal data, and the project should run at no ongoing cost.

## Options considered

1. **Hosted API** (Claude, GPT, Gemini): strongest models, but per-token cost, an API key to
   manage, and profiles leave the machine.
2. **Ollama, run natively**: one-command model pulls, an HTTP API and Python client, structured
   output via JSON schema, tool calling, and native GPU access on Windows/macOS.
3. **llama.cpp / vLLM directly**: more control and speed, but more setup and less convenient model
   management.

## Decision

Use Ollama, running natively on the host, with `qwen3:8b` as the default chat model and
`nomic-embed-text` for embeddings. The model name is configured in `.env`, so it can be swapped.

## Consequences

- Easier: free to run, works offline, profiles never leave the machine, models are easy to swap
  and compare in the Phase 9 eval.
- Harder: an 8B model is weaker than hosted models, so the design keeps the LLM on a short leash
  (validated structured output, scoring and filtering in plain Python). Needs a decent GPU for
  good latency, and CI cannot run the model.
