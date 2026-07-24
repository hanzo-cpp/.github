<div align="center">

# Hanzo for C++

**The Open AI Cloud — open source, every language, on-chain settlement.**

Native, modern-C++ access to the entire Hanzo cloud: models, agents, inference,
compute, data, network, security, platform, observability, apps.

[hanzo.ai](https://hanzo.ai) · [Docs](https://docs.hanzo.ai) · [C++ SDK wrapper](https://github.com/hanzoai/cpp-sdk) · [All SDKs](https://github.com/hanzoai/sdk)

</div>

---

## What's here

Hanzo ships **two SDK lines** for C++ — the same two lines we ship for every language:

- **Full Cloud SDK — [`hanzo-cpp/sdk`](https://github.com/hanzo-cpp/sdk)**
  The complete, idiomatic C++ client for the Hanzo cloud, generated from the
  cloud OpenAPI so it always covers all of `/v1`. This is what you install and
  build against. `find_package(hanzo)` and you have the whole platform.

- **AI / Agents SDK** — the hand-crafted flagship for building with models,
  agents, tools, memory, and MCP directly in C++. C++ is a first-class target
  in our completeness order (Python → Rust → **C++** → Go), and the agents
  library builds on the cloud SDK above.

Hanzo is a full AI SDK and AI cloud — not a proxy. **Zen** is our own model
family. Everything speaks `/v1/`.

## Install

CMake, via `find_package`:

```cmake
find_package(hanzo CONFIG REQUIRED)
target_link_libraries(app PRIVATE hanzo::hanzo)
```

## Usage

```cpp
#include <hanzo/hanzo.hpp>
#include <print>

int main() {
  hanzo::Client client{hanzo::from_env()};   // reads HANZO_API_KEY
  for (const auto& model : client.models().list())   // GET /v1/models
    std::println("{}", model.id);
}
```

Run an agent instead of listing models:

```cpp
auto reply = client.agents().run({.name = "researcher",
                                  .input = "Summarize the latest on fusion."});
std::println("{}", reply.output);
```

## Repositories

| Repo | What it is |
|------|------------|
| [`sdk`](https://github.com/hanzo-cpp/sdk) | Full Hanzo Cloud SDK for C++ — native bindings for agents, inference, and the whole `/v1` cloud. `find_package(hanzo)`. |

## Also available in

Per-language orgs carry the real, idiomatic code — because we genuinely adopt
and love each language:

[TypeScript / Node](https://github.com/hanzo-js) ·
[Go](https://github.com/hanzo-go) ·
[Python](https://github.com/hanzo-py) ·
[Rust](https://github.com/hanzo-rs) ·
[Swift](https://github.com/hanzo-swift) ·
[Kotlin](https://github.com/hanzo-kt) ·
[Hanzo (umbrella)](https://github.com/hanzoai)

The thin C++ wrapper / docs landing lives in the umbrella at
[`hanzoai/cpp-sdk`](https://github.com/hanzoai/cpp-sdk); the meta index of every
language is [`hanzoai/sdk`](https://github.com/hanzoai/sdk).

---

<div align="center">

**[Hanzo AI](https://hanzo.ai)** — the Open AI Cloud. Open source. Every language. On-chain settlement.

</div>
