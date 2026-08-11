<div align="center">

# AnoSys — AI Observability Platform

**One platform for agents, models, and infrastructure.**

[![Website](https://img.shields.io/badge/Website-anosys.ai-0A66C2?style=for-the-badge&logo=google-chrome&logoColor=white)](https://anosys.ai)
[![X](https://img.shields.io/badge/@AnosysAI-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/AnosysAI)
[![LinkedIn](https://img.shields.io/badge/Anosys--AI-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/anosys-ai/)
[![YouTube](https://img.shields.io/badge/@anosysai-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@anosysai)

</div>

---

## What is AnoSys?

AnoSys is a full-stack AI observability platform that ingests traces, metrics, logs, evals, and custom signals through **OpenTelemetry** and native SDKs. It gives teams one system of record across LLM calls, agent runs, tools, and infrastructure—without vendor lock-in or fragmented telemetry.

Add a few lines of code and every OpenAI call, OpenAI Agents run, custom function, and Claude Code session can be captured and sent to your AnoSys workspace.

## ✨ Platform Capabilities

| Capability | Description |
| :--- | :--- |
| **Observability Platform** | Ingest traces, metrics, logs, evals, and custom signals across models, agents, and infrastructure |
| **Anomaly Detection** | Detect silent failures, cost spikes, latency drift, and abuse patterns in real time |
| **Continuous Evals** | Run evaluations in CI and production to catch accuracy, safety, and policy regressions |
| **Custom Pipelines** | Enrich, route, and transform signals; trigger actions on anomalies or policy violations |
| **Root Cause Analysis** | Trace failures across agents, models, tools, and infrastructure to identify why they happened |
| **Alerting & Incidents** | Route alerts with context, ownership, and escalation from detection through resolution |
| **Dashboards & KPIs** | Monitor model health, agent reliability, latency, token usage, and cost with drill-down views |
| **Natural Language Interface** | Ask questions in plain English, generate queries, and summarize incidents |

## 🎯 Solutions

<table>
<tr>
<td><b>AI Systems</b></td>
<td>Agentic AI · Foundation Models · AI Safety & Compliance</td>
</tr>
<tr>
<td><b>Security & Fraud</b></td>
<td>Network Security · Online Advertising & Fraud · National Defense</td>
</tr>
<tr>
<td><b>Operations & Scale</b></td>
<td>Infrastructure Monitoring · IoT & Streaming Analytics</td>
</tr>
</table>

## 📦 Official AnoSys SDK

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![CI](https://github.com/anosys-ai/anosys-sdk/actions/workflows/ci.yml/badge.svg)](https://github.com/anosys-ai/anosys-sdk/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/downloads/)
[![Node.js](https://img.shields.io/badge/node-%E2%89%A518-green.svg)](https://nodejs.org/)

The [`anosys-sdk`](https://github.com/Anosys-AI/anosys-sdk) repository contains the official modular Python and JavaScript SDKs for AnoSys.

### Python

| Package | Version | Description | Install |
|---------|---------|-------------|---------|
| [`anosys-sdk-core`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/core) | 1.0.13 | Shared config, HTTP client, decorators, and data models | `pip install anosys-sdk-core` |
| [`anosys-sdk-openai`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai) | 1.0.13 | OpenAI SDK instrumentation through OpenTelemetry | `pip install anosys-sdk-openai` |
| [`anosys-sdk-openai-agents`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai_agents) | 1.0.12 | OpenAI Agents SDK tracing processor | `pip install anosys-sdk-openai-agents` |
| [`anosys-claude-code`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_code) | 0.2.8 | Claude Code observability hook and CLI | `pip install anosys-claude-code` |

### JavaScript / Node.js

| Package | Version | Description | Install |
|---------|---------|-------------|---------|
| [`anosys-sdk-openai`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai) | 1.0.11 | OpenAI SDK instrumentation through OpenTelemetry | `npm install anosys-sdk-openai` |
| [`anosys-sdk-openai-agents`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/openai-agents) | 1.0.11 | OpenAI Agents SDK tracing processor | `npm install anosys-sdk-openai-agents` |
| [`anosys-sdk-claude-code`](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/js/claude-code) | 0.2.5 | Claude Code observability hook and CLI | `npx anosys-sdk-claude-code install` |

## 🚀 Quick Start

### Prerequisites

1. Sign up at [anosys.ai](https://anosys.ai).
2. Get your AnoSys API key from the [integration options page](https://console.anosys.ai/collect/integrationoptions).
3. Export the keys required by your integration:

```bash
export ANOSYS_API_KEY="your-anosys-key"
export OPENAI_API_KEY="your-openai-key"
```

### OpenAI — Python

```bash
pip install anosys-sdk-openai
```

```python
from openai import OpenAI
from anosys_sdk_openai import AnosysOpenAILogger

# Initialize once—subsequent OpenAI calls are captured automatically.
AnosysOpenAILogger()

client = OpenAI()
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Hello!"}],
)
print(response.choices[0].message.content)
```

### OpenAI — JavaScript

```bash
npm install anosys-sdk-openai openai
```

```js
import { AnosysOpenAILogger } from 'anosys-sdk-openai';
import OpenAI from 'openai';

new AnosysOpenAILogger();

const client = new OpenAI();
const response = await client.chat.completions.create({
  model: 'gpt-4o',
  messages: [{ role: 'user', content: 'Hello!' }],
});
```

### OpenAI Agents

<table>
<tr>
<td><b>Python</b></td>
<td><code>pip install anosys-sdk-openai-agents</code></td>
</tr>
<tr>
<td><b>JavaScript</b></td>
<td><code>npm install anosys-sdk-openai-agents @openai/agents</code></td>
</tr>
</table>

See the [`anosys-sdk` quick start](https://github.com/Anosys-AI/anosys-sdk#openai-agents--python) for complete Python and JavaScript examples.

### Claude Code

Install the Python or JavaScript integration and run its setup wizard:

```bash
# Python
pip install anosys-claude-code
anosys-claude-code install

# JavaScript / Node.js
npx anosys-sdk-claude-code install
```

The installer registers a Claude Code `Stop` hook, incrementally maps new messages and subagent events, applies optional content redaction, and batches telemetry to your AnoSys workspace.

### Custom Function Logging

```python
from anosys_sdk_core import anosys_logger

@anosys_logger(source="my_app")
def my_function(data):
    return process(data)
```

## 🏗️ Architecture

```text
┌──────────────────────────────┐
│ Your AI application         │
│ Models · Agents · Tools     │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│ AnoSys SDKs & OpenTelemetry │
│ Python · JavaScript · Hooks │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│ AnoSys ingestion platform   │
│ Traces · Metrics · Logs     │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│ Detection & investigation   │
│ Evals · RCA · Alerts · KPIs │
└──────────────────────────────┘
```

## 📂 More Open-Source Projects

- [`AnoSys-Demo-Customer`](https://github.com/Anosys-AI/AnoSys-Demo-Customer) — agentic luxury real-estate demo built with ChatKit and context-aware AI assistants.
- [`anosys-logger-4-openai`](https://github.com/Anosys-AI/anosys-logger-4-openai) — earlier standalone OpenAI logger for Python and Node.js.
- [`anosys-logger-4-openai-agents`](https://github.com/Anosys-AI/anosys-logger-4-openai-agents) — earlier standalone OpenAI Agents SDK integration.

For current integrations and releases, use the unified [`anosys-sdk`](https://github.com/Anosys-AI/anosys-sdk).

## 📚 Resources

- 🌐 **Website:** [anosys.ai](https://anosys.ai)
- 📖 **Documentation:** [docs.anosys.ai](https://docs.anosys.ai)
- 🎮 **Console:** [console.anosys.ai](https://console.anosys.ai)
- 🔌 **Integration options:** [console.anosys.ai/collect/integrationoptions](https://console.anosys.ai/collect/integrationoptions)
- 💻 **SDK:** [github.com/Anosys-AI/anosys-sdk](https://github.com/Anosys-AI/anosys-sdk)
- 📧 **Support:** [support@anosys.ai](mailto:support@anosys.ai)

## 📝 License

Individual repositories are licensed under their own terms. The official AnoSys SDK is released under the **Apache 2.0** license.

---

<div align="center">

**Built with ❤️ by the AnoSys team — United States 🇺🇸**
<img src="https://api.anosys.ai/trafficpixel/925fb3f78b04d5b9d5aded56b44410c9/a/ea8a7985c8f3/anosys.gif?cvs198=https://github.com/Anosys-AI" width="1" height="1" alt=""/>
</div>
