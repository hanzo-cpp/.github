# LLM.md — hanzo-cpp

Machine-oriented guide for AI agents / coding assistants working in this org.

## What this org is

`hanzo-cpp` is the **per-language org for C++** in the Hanzo ecosystem. It holds
the REAL, idiomatic C++ code. Hanzo is the **Open AI Cloud** — a full AI SDK and
AI cloud, not a proxy.

## Canonical SDK model (two lines, every language)

1. **Full Cloud SDK** — generated from the cloud OpenAPI, covers all of `/v1`.
   Real code lives here as **`hanzo-cpp/sdk`**. A thin wrapper/docs landing lives
   in the umbrella as `hanzoai/cpp-sdk`. Meta index: `hanzoai/sdk`.
2. **AI / Agents SDK** — hand-crafted flagship (models, agents, tools, memory,
   MCP, inference). Completeness order: Python → Rust → C++ → Go.

## Where real code lives

- Full cloud SDK: **`hanzo-cpp/sdk`** — build against this.

## Install

```cmake
find_package(hanzo CONFIG REQUIRED)
target_link_libraries(app PRIVATE hanzo::hanzo)
```

## Brand rules (hard — never violate)

- NEVER call Hanzo an "LLM gateway"; NEVER position against LiteLLM. It is a full
  AI SDK / AI cloud.
- **Zen** models are our own family — never name upstream models.
- API paths are **`/v1/`** only — never an `/api/` prefix.
- Positioning: "Hanzo — the Open AI Cloud. Open source. Every language. On-chain settlement."

## Source of truth

Full architecture: `~/work/hanzo/SDK-ARCHITECTURE.md`.
