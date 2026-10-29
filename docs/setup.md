# Setup

Exact steps to get a fresh machine ready to develop travel-ai.
The full `make up` walkthrough arrives in Phase 2.

## Requirements

- 16 GB RAM minimum. A GPU with 8 GB+ VRAM runs an 8B model comfortably; CPU-only works but is slow.
- Windows 11, macOS or Linux.

## Tools

Versions used during development (2026-10-29):

| Tool           | Version   | Install                                                        |
| -------------- | --------- | -------------------------------------------------------------- |
| Git            | 2.56.0    | <https://git-scm.com>                                          |
| GitHub CLI     | 2.103.3   | <https://cli.github.com>, then `gh auth login`                 |
| Python         | 3.12      | managed by uv (`.python-version`)                              |
| uv             | 0.13.6    | <https://docs.astral.sh/uv/>                                   |
| Ollama         | 0.40.13   | <https://ollama.com>, natively on your OS for GPU access       |
| Docker Desktop | _TODO_    | <https://www.docker.com/products/docker-desktop/> (WSL2 backend on Windows) |

Recommended VS Code extensions: Python, Pylance, Ruff, Docker (Container Tools), GitLens,
markdownlint, Mermaid preview.

## Models

```bash
ollama pull qwen3:8b
ollama pull nomic-embed-text
```

## Clone and install

```bash
git clone https://github.com/Zoken910/travel-ai.git
cd travel-ai
uv sync                       # creates .venv with app + dev dependencies
uv run pre-commit install     # Ruff lint/format on every commit
cp .env.example .env          # then edit values
```

## Check that everything works

```bash
docker run hello-world
ollama run qwen3:8b "hi"
gh auth status
uv run pre-commit run --all-files
```

## Notes

- Tool-calling smoke test (`get_weather` with `qwen3:8b`): _TODO: record whether the model calls
  the tool reliably._
