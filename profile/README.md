<div align="center">

# AnoSys

**AI Operational Intelligence for production AI systems**

[Website](https://anosys.ai) · [Documentation](https://docs.anosys.ai) · [Console](https://console.anosys.ai) · [LinkedIn](https://www.linkedin.com/company/anosys-ai/) · [X](https://x.com/AnosysAI) · [YouTube](https://www.youtube.com/@anosysai)

</div>

## Understand what your AI is doing in production

AnoSys helps teams operate agents, models, AI applications, and AI-powered business workflows after they go live.

We bring traces, metrics, logs, evals, LLM calls, cost, user behavior, governance context, and business outcomes into one operational context layer. When something changes or breaks, teams can move from "we have a problem" to understanding why it happened, who it affected, what it cost, and what to do next.

Observability tells you what happened. AnoSys helps you understand what it means and act on it.

## From signals to action

| | What AnoSys does |
| :--- | :--- |
| **Observe** | Capture telemetry from models, agents, tools, infrastructure, users, and business processes. |
| **Understand** | Detect anomalies, run continuous evals, explain root causes, and connect technical behavior to cost and business impact. |
| **Act** | Alert the right owner, apply governance rules, trigger pipelines, and recommend the next step. |

Teams use AnoSys to:

- Debug agent runs across models, tools, handoffs, and retries.
- Find silent quality regressions before they become customer problems.
- Attribute token and infrastructure spend to the features, users, and workflows creating it.
- Monitor customer experience and business processes alongside technical health.
- Govern sensitive data and production AI behavior.
- Ask questions in plain English and get answers grounded in operational data.

## Connect the stack you already use

AnoSys accepts OpenTelemetry OTLP/HTTP, OpenTelemetry Collector data, REST API events, native SDK telemetry, browser and JavaScript events, image pixels, and data from cloud storage. You can start with one application and expand without rebuilding your instrumentation around a proprietary format.

## Official SDKs

The [`anosys-sdk`](https://github.com/Anosys-AI/anosys-sdk) repository contains the official modular Python and JavaScript integrations.

### Python

| Package | Version | Use it for | Install |
| :--- | :--- | :--- | :--- |
| [`anosys-sdk-core`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/core) | 1.0.13 | Shared configuration, HTTP transport, decorators, and data models | `pip install anosys-sdk-core` |
| [`anosys-sdk-openai`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai) | 1.0.13 | OpenAI SDK instrumentation through OpenTelemetry | `pip install anosys-sdk-openai` |
| [`anosys-sdk-openai-agents`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai_agents) | 1.0.12 | OpenAI Agents SDK tracing | `pip install anosys-sdk-openai-agents` |
| [`anosys-claude-code`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_code) | 0.2.8 | Claude Code session observability | `pip install anosys-claude-code` |

### JavaScript and Node.js

| Package | Version | Use it for | Install |
| :--- | :--- | :--- | :--- |
| [`anosys-sdk-openai`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai) | 1.0.11 | OpenAI SDK instrumentation through OpenTelemetry | `npm install anosys-sdk-openai` |
| [`anosys-sdk-openai-agents`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai-agents) | 1.0.11 | OpenAI Agents SDK tracing | `npm install anosys-sdk-openai-agents` |
| [`anosys-sdk-claude-code`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/claude-code) | 0.2.5 | Claude Code session observability | `npx anosys-sdk-claude-code install` |

## Get started

Create an account at [anosys.ai](https://anosys.ai), then get an API key from the [integration options page](https://console.anosys.ai/collect/integrationoptions).

```bash
export ANOSYS_API_KEY="your-anosys-key"
```

### OpenAI with Python

```bash
pip install anosys-sdk-openai
```

```python
from openai import OpenAI
from anosys_sdk_openai import AnosysOpenAILogger

AnosysOpenAILogger()

client = OpenAI()
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Hello!"}],
)
```

### OpenAI with JavaScript

```bash
npm install anosys-sdk-openai openai
```

```js
import { AnosysOpenAILogger } from 'anosys-sdk-openai';
import OpenAI from 'openai';

new AnosysOpenAILogger();

const client = new OpenAI();
const response = await client.chat.completions.create({
  model: 'gpt-4o-mini',
  messages: [{ role: 'user', content: 'Hello!' }],
});
```

### Claude Code

Use either integration to install the AnoSys hook:

```bash
# Python
pip install anosys-claude-code
anosys-claude-code install

# JavaScript and Node.js
npx anosys-sdk-claude-code install
```

The hook captures new conversation and subagent events, supports optional content reduction, and sends telemetry to your AnoSys workspace in batches.

For OpenAI Agents, custom function logging, configuration, and complete examples, see the [SDK documentation](https://github.com/Anosys-AI/anosys-sdk#readme).

## Open-source projects

- [`anosys-sdk`](https://github.com/Anosys-AI/anosys-sdk) — current Python and JavaScript integrations.
- [`AnoSys-Demo-Customer`](https://github.com/Anosys-AI/AnoSys-Demo-Customer) — an agentic real-estate application showing AnoSys in a working product.
- [`anosys-logger-4-openai`](https://github.com/Anosys-AI/anosys-logger-4-openai) — the earlier standalone OpenAI logger for Python and Node.js.
- [`anosys-logger-4-openai-agents`](https://github.com/Anosys-AI/anosys-logger-4-openai-agents) — the earlier standalone OpenAI Agents integration.

New integrations and releases are published in [`anosys-sdk`](https://github.com/Anosys-AI/anosys-sdk).

## Resources

- [Product website](https://anosys.ai)
- [Documentation](https://docs.anosys.ai)
- [AnoSys Console](https://console.anosys.ai)
- [Integration options](https://console.anosys.ai/collect/integrationoptions)
- [Support](mailto:support@anosys.ai)

## License

Each repository is licensed under its own terms. The official AnoSys SDK uses the [Apache License 2.0](https://github.com/Anosys-AI/anosys-sdk/blob/main/LICENSE).

<img src="https://api.anosys.ai/trafficpixel/925fb3f78b04d5b9d5aded56b44410c9/a/ea8a7985c8f3/anosys.gif?cvs198=https://github.com/Anosys-AI" width="1" height="1" alt=""/>
