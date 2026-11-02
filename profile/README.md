# Anosys.AI

**AI Operational Intelligence Platform**

[Website](https://anosys.ai) · [Documentation](https://docs.anosys.ai) · [Console](https://console.anosys.ai) · [LinkedIn](https://www.linkedin.com/company/anosys-ai/) · [X](https://x.com/AnosysAI) · [YouTube](https://www.youtube.com/@anosysai)

## Understand what changes in production AI

Anosys brings agent traces, evaluations, token spend, and web and product analytics into the same operational context. Teams can investigate a quality regression, trace it to a model or tool call, identify the users and workflows affected, and check whether a fix worked.

The platform connects technical behavior with cost, user experience, and business outcomes. It supports trace timelines and trees, evaluations on production traffic, anomaly detection, root-cause analysis, dashboards, alerts, scheduled pipelines, and an AI Assistant for investigating operational data.

## Connect your applications and agents

The official [AnoSys SDK](https://github.com/Anosys-AI/anosys-sdk) provides modular Python and JavaScript integrations.

| Integration | Python package | JavaScript package |
| --- | --- | --- |
| OpenAI API | [anosys-sdk-openai](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai) | [anosys-sdk-openai](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai) |
| OpenAI Agents SDK | [anosys-sdk-openai-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai_agents) | [anosys-sdk-openai-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai-agents) |
| Anthropic API | [anosys-sdk-anthropic](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/anthropic) | [anosys-sdk-anthropic](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/anthropic) |
| Claude Agent SDK | [anosys-sdk-claude-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_agents) | [anosys-sdk-claude-agents](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/claude-agents) |
| Claude Code | [anosys-claude-code](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_code) | [anosys-sdk-claude-code](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/claude-code) |
| Codex CLI | [anosys-codex](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/codex) | [anosys-sdk-codex](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/codex) |
| Antigravity | [anosys-antigravity](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/antigravity) | [anosys-sdk-antigravity](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/antigravity) |
| Custom Python logging | [anosys-sdk-core](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/core) | Decorators are included in the API integrations |

See the [SDK package list](https://github.com/Anosys-AI/anosys-sdk#published-packages) for current versions, requirements, and installation commands.

Antigravity collects agent activity, tool calls, commands, files, and duration. Its hook inputs and transcripts do not expose token counters or cost. Read the [Antigravity setup guide](https://github.com/Anosys-AI/anosys-sdk/blob/main/ANTIGRAVITY.md) for global and workspace installation, content redaction, and diagnostics.

You can also send data through OpenTelemetry OTLP/HTTP, the OpenTelemetry Collector, REST APIs, JavaScript tracking, image pixels, and file ingestion. SDK instrumentation and coding-tool hooks use different endpoint types; the [integration options page](https://console.anosys.ai/collect/integrationoptions) provides the appropriate keys.

## Get started

1. Create an account at [anosys.ai](https://anosys.ai).
2. Create an endpoint and get its key from [integration options](https://console.anosys.ai/collect/integrationoptions).
3. Install the package for your application or coding tool and follow its setup guide.

For example, install Anthropic API instrumentation:

```bash
# Python
pip install anosys-sdk-anthropic

# JavaScript
npm install anosys-sdk-anthropic @anthropic-ai/sdk
```

For agent workflows, use the Claude Agent SDK or OpenAI Agents SDK integration. For developer-tool activity, use the Claude Code or Codex CLI integration. The [SDK README](https://github.com/Anosys-AI/anosys-sdk#readme) links to examples and complete setup instructions.

## Control sensitive telemetry

The OpenAI, Anthropic, Claude Agents, Claude Code, and Codex integrations support opt-in encryption of selected string fields before transmission. Anthropic and Claude Agents integrations offer content-capture controls; coding-tool hooks offer content redaction. Antigravity 0.1.0 supports redaction but does not implement field encryption. These controls have different scopes and do not guarantee that every field in a payload is encrypted or masked.

Encryption uses the SDK's existing AES-256-CBC compatibility format. Decryption settings in the browser are configured separately. Read the [SDK content-controls reference](https://github.com/Anosys-AI/anosys-sdk/blob/main/DATA_CONTROLS.md) before collecting sensitive data.

## Open-source repositories

- [anosys-sdk](https://github.com/Anosys-AI/anosys-sdk): current Python and JavaScript integrations, examples, and telemetry references.
- [AnoSys-Demo-Customer](https://github.com/Anosys-AI/AnoSys-Demo-Customer): an agentic real-estate application demonstrating AnoSys in a working product.
- [anosys-logger-4-openai](https://github.com/Anosys-AI/anosys-logger-4-openai) and [anosys-logger-4-openai-agents](https://github.com/Anosys-AI/anosys-logger-4-openai-agents): earlier standalone integrations. Use anosys-sdk for new work.

## Resources

[Product](https://anosys.ai) · [Documentation](https://docs.anosys.ai) · [SDK](https://github.com/Anosys-AI/anosys-sdk) · [Console](https://console.anosys.ai) · [Support](mailto:support@anosys.ai)

Each repository has its own license. The official SDK uses the [Apache License 2.0](https://github.com/Anosys-AI/anosys-sdk/blob/main/LICENSE).

<img src="https://api.anosys.ai/trafficpixel/925fb3f78b04d5b9d5aded56b44410c9/a/ea8a7985c8f3/anosys.gif?cvs198=https://github.com/Anosys-AI" width="1" height="1" alt=""/>
