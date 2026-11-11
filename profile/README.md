# Anosys.ai — AI Operational Intelligence Platform

[Website](https://anosys.ai) · [Documentation](https://docs.anosys.ai) · [Console](https://console.anosys.ai) · [LinkedIn](https://www.linkedin.com/company/anosys-ai/) · [X](https://x.com/AnosysAI) · [YouTube](https://www.youtube.com/@anosysai)

## Connect AI operations to business outcomes

Anosys.ai brings AI observability, continuous evaluation, anomaly detection, root-cause analysis, and web and product analytics into one platform. It connects the behavior of models, agents, tools, and applications with quality, reliability, cost, user experience, and business outcomes.

Teams use Anosys.ai to monitor operations, evaluate performance, investigate failures, manage spend, and measure the impact of their AI systems. Engineers, product teams, and business operators work from the same operational context, from an individual model call to the workflow and customer journey it supports.

## From telemetry to operational decisions

- **Observe AI systems end to end.** Explore model calls, agent runs, tool activity, errors, latency, token usage, and estimated cost through trace timelines and trees.
- **Evaluate quality and reliability.** Run evaluations on production traffic and detect anomalies in behavior, performance, and spend.
- **Investigate causes and impact.** Connect technical failures with affected users and workflows, and use the AI Assistant to explore operational data in natural language.
- **Connect AI performance with product and business performance.** Bring web and product analytics alongside AI telemetry to understand user experience and business outcomes.
- **Put insights to work.** Use dashboards, alerts, and scheduled data pipelines to monitor priorities, surface issues, and verify whether changes deliver the intended results.

The SDKs in this organization provide the instrumentation layer. The Anosys.ai platform brings those signals together with evaluations and application data to support operational decisions across teams.

## Connect your applications and agents

The official [Anosys.ai SDK](https://github.com/Anosys-AI/anosys-sdk) provides modular Python and JavaScript integrations.

| Integration | Python package | JavaScript package |
| --- | --- | --- |
| OpenAI API | [anosys-sdk-openai](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai) | [anosys-sdk-openai](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai) |
| OpenAI Agents SDK | [anosys-sdk-openai-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai_agents) | [anosys-sdk-openai-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai-agents) |
| Anthropic API | [anosys-sdk-anthropic](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/anthropic) | [anosys-sdk-anthropic](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/anthropic) |
| Claude Agent SDK | [anosys-sdk-claude-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_agents) | [anosys-sdk-claude-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/claude-agents) |
| Claude Code | [anosys-claude-code](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_code) | [anosys-sdk-claude-code](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/claude-code) |
| Codex CLI | [anosys-codex](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/codex) | [anosys-sdk-codex](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/codex) |
| Antigravity | [anosys-antigravity](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/antigravity) | [anosys-sdk-antigravity](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/antigravity) |
| Core and custom logging | [anosys-sdk-core](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/core) | [anosys-sdk-core](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/core) |

See the [SDK package list](https://github.com/Anosys-AI/anosys-sdk#published-packages) for current versions, requirements, and installation commands.

Antigravity collects agent activity, tool calls, commands, files, and duration. Its hook inputs and transcripts do not expose token counters or cost. Read the [Antigravity setup guide](https://github.com/Anosys-AI/anosys-sdk/blob/main/ANTIGRAVITY.md) for global and workspace installation, collection levels, and diagnostics.

You can also send data through OpenTelemetry OTLP/HTTP, the OpenTelemetry Collector, REST APIs, JavaScript tracking, image pixels, and file ingestion. SDK instrumentation and coding-tool hooks use different endpoint types; the [integration options page](https://console.anosys.ai/collect/integrationoptions) provides the appropriate keys.

## Get started

1. Create an account at [Anosys.ai](https://anosys.ai).
2. Create an endpoint and get its key from [integration options](https://console.anosys.ai/collect/integrationoptions).
3. Install the package for your application or coding tool and follow its setup guide.

For example, install Anthropic API instrumentation:

```bash
# Python
pip install anosys-sdk-anthropic

# JavaScript
npm install anosys-sdk-anthropic @anthropic-ai/sdk
```

For agent workflows, use the Claude Agent SDK or OpenAI Agents SDK integration. For developer-tool activity, use the Claude Code, Codex CLI, or Antigravity integration. The [SDK README](https://github.com/Anosys-AI/anosys-sdk#readme) links to examples and complete setup instructions.

## Control sensitive telemetry

All integrations share collection levels: `off`, `metadata`, and `full`. Coding-tool hooks default to metadata only; collecting full content requires each user to accept the data collection policy. Application SDKs default to full collection, with developer controls to reduce or disable it. Project settings can lower collection but cannot override a user's more restrictive choice.

Every integration, including Antigravity, supports opt-in client-side encryption before transmission. The `enc2` format uses PBKDF2-SHA256 and deterministic AES-256-GCM with a workspace salt; metadata remains readable, and deterministic ciphertext allows grouping and joins while revealing equality between values. Browser decryption must support the same format, passphrase, and salt. Read the [SDK content-controls reference](https://github.com/Anosys-AI/anosys-sdk/blob/main/DATA_CONTROLS.md) and [upgrade notes](https://github.com/Anosys-AI/anosys-sdk/blob/main/RELEASE_NOTES.md) before rollout.

## Open-source repositories

- [anosys-sdk](https://github.com/Anosys-AI/anosys-sdk): current Python and JavaScript integrations, examples, and telemetry references.
- [Demo application](https://github.com/Anosys-AI/AnoSys-Demo-Customer): an agentic real-estate application demonstrating Anosys.ai in a working product.
- [anosys-logger-4-openai](https://github.com/Anosys-AI/anosys-logger-4-openai) and [anosys-logger-4-openai-agents](https://github.com/Anosys-AI/anosys-logger-4-openai-agents): earlier standalone integrations. Use anosys-sdk for new work.

## Resources

[Product](https://anosys.ai) · [Documentation](https://docs.anosys.ai) · [SDK](https://github.com/Anosys-AI/anosys-sdk) · [Console](https://console.anosys.ai) · [Support](mailto:support@anosys.ai)

Each repository has its own license. The official SDK uses the [Apache License 2.0](https://github.com/Anosys-AI/anosys-sdk/blob/main/LICENSE).

<img src="https://api.anosys.ai/trafficpixel/925fb3f78b04d5b9d5aded56b44410c9/a/ea8a7985c8f3/anosys.gif?cvs198=https://github.com/Anosys-AI" width="1" height="1" alt=""/>
