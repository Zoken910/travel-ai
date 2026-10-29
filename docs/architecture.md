# Architecture

_Filled in during Phases 2, 6 and 10._

## Components

```mermaid
flowchart LR
    UI[Streamlit app] --> ORCH[Orchestrator]
    ORCH --> LLM[Ollama]
    ORCH --> MCP[MCP servers<br/>search · transport · stays · places]
    ORCH --> DB[(PostgreSQL)]
    MCP --> WEB[SearXNG / travel APIs]
```

The orchestrator is the only component that talks to the LLM and the MCP servers; profiles stay
in Postgres on your machine.

## Pipeline

_Phase 6: parse → gather → filter → score → write, as a sequence diagram._
