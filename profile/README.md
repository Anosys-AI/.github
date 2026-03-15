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

AnoSys is a full-stack AI observability platform that ingests traces, metrics, logs, evals, and custom signals via **OpenTelemetry** or native SDKs — giving you a single system of record across every framework. Whether you run LangChain, CrewAI, OpenAI Agents SDK, or custom instrumentation, AnoSys normalizes everything into a unified backend. No vendor lock-in, no data silos.

## ✨ Platform Capabilities

| Capability | Description |
| :--- | :--- |
| **Observability Platform** | Ingest traces, metrics, logs, evals, and custom signals — one system of record across every framework |
| **Anomaly Detection** | Spot silent failures, cost spikes, latency drift, and abuse patterns in real time |
| **Continuous Evals** | Run evals in CI and production; catch accuracy drops, safety violations, and policy drift |
| **Custom Pipelines** | Enrich, route, and transform signals without glue code; trigger actions on anomalies or policy violations |
| **Root Cause Analysis** | Go from "something broke" to "here's why" — causal paths across agents, models, and infrastructure |
| **Alerting & Incidents** | Context-aware routing, auto-escalation, and ownership tracking from detection to resolution |
| **Dashboards & KPIs** | Pre-built views for model health, agent reliability, and cost — with drill-downs for debugging |
| **Natural Language Interface** | Ask questions in plain English, auto-generate queries, and summarize incidents |

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

## 📦 Open-Source Repositories

### [`anosys-sdk`](https://github.com/Anosys-AI/anosys-sdk) — Instrumentation SDK

The unified Python SDK for AnoSys. Ships as modular packages you can install independently:

```
pip install anosys-sdk-core          # Core decorator & logger
pip install anosys-sdk-openai        # OpenAI API auto-instrumentation
pip install anosys-sdk-openai-agents # OpenAI Agents SDK integration
```

**Quick start — OpenAI integration:**

```python
from openai import OpenAI
from anosys_sdk_openai import AnosysOpenAILogger

AnosysOpenAILogger()                       # Initialize once

client = OpenAI()
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Hello!"}]
)
# Calls are automatically logged to AnoSys ✨
```

**Quick start — OpenAI Agents:**

```python
from agents import Agent, Runner, set_tracing_processor
from anosys_sdk_openai_agents import AnosysOpenAIAgentsLogger

set_tracing_processor(AnosysOpenAIAgentsLogger())

agent = Agent(name="Assistant", instructions="You are helpful.")
result = Runner.run_sync(agent, "Hello!")
```

**Quick start — Custom function logging:**

```python
from anosys_sdk_core import anosys_logger

@anosys_logger(source="my_app")
def my_function(data):
    return process(data)
```

> License: Apache 2.0

---

### [`anosys-logger-4-openai`](https://github.com/Anosys-AI/anosys-logger-4-openai) — OpenAI Logger (Python & Node.js)

Automatic observability for OpenAI API calls with zero-config instrumentation. Available for both **Python** and **Node.js**.

**Key features:**
- ✅ Zero-config instrumentation — just install and use
- ✅ Full streaming support with chunk aggregation
- ✅ OpenTelemetry Gen AI semantic conventions
- ✅ Custom decorators for any function (sync or async)
- ✅ Error tracking with full stack traces
- ✅ Distributed tracing with trace IDs

---

### [`anosys-logger-4-openai-agents`](https://github.com/Anosys-AI/anosys-logger-4-openai-agents) — OpenAI Agents Logger

Observability integration for the OpenAI Agents SDK — trace tool calls, agent decisions, and multi-agent handoffs.

---

### [`AnoSys-Demo-Customer`](https://github.com/Anosys-AI/AnoSys-Demo-Customer) — Demo Application

A live showcase of AnoSys agentic capabilities built around a luxury real-estate experience (Elysian Estates). Demonstrates intelligent chat orchestration with `@openai/chatkit-react`, agentic workflows for complex inquiries, and context-aware AI assistants.

## 🏗️ Architecture

```
┌─────────────────┐
│  Your App Code  │
└────────┬────────┘
         │
         ▼
┌─────────────────┐     ┌──────────────────┐
│  AnoSys Logger  │────▶│  OpenTelemetry   │
│  (Interceptor)  │     │ Instrumentation  │
└────────┬────────┘     └──────────────────┘
         │
         ▼
┌─────────────────┐
│   OpenAI API    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   AnoSys API    │
│   (Telemetry)   │
└─────────────────┘
```

## 🚀 Getting Started

1. **Sign up** at [console.anosys.ai](https://console.anosys.ai) and grab your API key.
2. **Install** the SDK package for your framework:
   ```bash
   pip install anosys-sdk-openai
   ```
3. **Set environment variables:**
   ```bash
   export ANOSYS_API_KEY="your-anosys-key"
   export OPENAI_API_KEY="your-openai-key"
   ```
4. **Initialize** the logger and use your AI framework normally — calls are captured automatically.

## 📚 Resources

- 🌐 **Website:** [anosys.ai](https://anosys.ai)
- 📖 **Documentation:** [docs.anosys.ai](https://docs.anosys.ai)
- 🎮 **Console:** [console.anosys.ai](https://console.anosys.ai)
- 📧 **Support:** [support@anosys.ai](mailto:support@anosys.ai)

## 📝 License

Individual repositories are licensed under their own terms. The primary SDK is released under the **Apache 2.0** license. See each repository for details.

---

<div align="center">

**Built with ❤️ by the AnoSys team — United States 🇺🇸**

</div>
