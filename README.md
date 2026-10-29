# travel-ai

A local-first AI travel planner: tell it your budget, dates and travel style, and a local LLM
turns real travel data into three ranked plans (cheapest, fastest, most comfortable), with the
source and timestamp of every price.

> 🚧 Work in progress: currently at **Phase 1, repo and documentation scaffold**. See the
> [Roadmap](#roadmap).

## Overview

_Coming soon: one-line pitch and demo GIF._

## Features

_Coming soon._

## Architecture

_Coming soon. See [docs/architecture.md](docs/architecture.md)._

## Quickstart

_Coming in Phase 2 (`make up`). Until then, see [docs/setup.md](docs/setup.md)._

## Tech stack

| Layer         | Tool                                   |
| ------------- | -------------------------------------- |
| LLM           | [Ollama](https://ollama.com) (`qwen3:8b`), run locally |
| Tools / data  | MCP servers (official `mcp` Python SDK) |
| UI            | Streamlit                              |
| Database      | PostgreSQL + pgvector, SQLAlchemy, Alembic |
| Tooling       | uv, Ruff, pytest, pre-commit, Docker Compose |

## Data sources

_Coming soon. See [docs/data-sources.md](docs/data-sources.md)._

## Roadmap

- [x] Phase 0: Prerequisites
- [x] Phase 1: GitHub repo and documentation scaffold
- [ ] Phase 2: Docker infrastructure
- [ ] Phase 3: Data models and database
- [ ] Phase 4: Streamlit preference interface
- [ ] Phase 5: MCP servers with mock data
- [ ] Phase 6: Orchestrator pipeline, first vertical slice (`v0.1.0`)
- [ ] Phase 7: Real data sources
- [ ] Phase 8: Results UI, three plans and refinement (`v0.2.0`)
- [ ] Phase 9: Testing, evaluation and CI
- [ ] Phase 10: Polish and release (`v1.0.0`)

## Limitations

_Coming soon._

## License

[MIT](LICENSE)
