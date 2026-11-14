<p align="center">
  <a href="https://anosys.ai">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/anosys-new-white-darkmode.svg">
      <img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/anosys-new-black-lightmode.svg" alt="Anosys.ai" width="360">
    </picture>
  </a>
</p>

<p align="center"><b>The AI Operational Intelligence Platform</b></p>

<p align="center">
  <a href="https://anosys.ai">Website</a> · <a href="https://docs.anosys.ai">Documentation</a> · <a href="https://console.anosys.ai">Console</a> · <a href="https://github.com/Anosys-AI/anosys-sdk">SDK</a> · <a href="https://www.linkedin.com/company/anosys-ai/">LinkedIn</a> · <a href="https://x.com/AnosysAI">X</a> · <a href="https://www.youtube.com/@anosysai">YouTube</a>
</p>

Anosys.ai shows you what your AI is doing and what it costs. One platform for AI observability, evaluations, anomaly detection, root-cause analysis and product analytics, connected to the outcomes your business cares about.

- **See every model call and agent run**, with tool calls, errors, latency, tokens and cost.
- **Catch problems early** with evaluations on live traffic and anomaly alerts on quality, performance and spend.
- **Find the cause fast**: trace a failure from the model call to the users and workflows it affected, or ask the AI Assistant in plain language.
- **Measure impact**: put AI performance next to web and product analytics, on dashboards your whole team uses.

## Get started

1. Create an account at [anosys.ai](https://anosys.ai) and get a key from [Integration options](https://console.anosys.ai/collect/integrationoptions).
2. Install the integration for your stack and add one line:

   ```bash
   pip install anosys-sdk-openai      # or: npm install anosys-sdk-openai openai
   ```

   ```python
   from anosys_sdk_openai import AnosysOpenAILogger
   AnosysOpenAILogger()  # every OpenAI call from here on is traced
   ```

3. Open the [Console](https://console.anosys.ai) to see your traces.

The [SDK quickstart](https://github.com/Anosys-AI/anosys-sdk#quickstart) has the full example in Python and JavaScript.

## Integrations

| Integration | Example use cases |
| --- | --- |
| <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/openai-dark.svg"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/openai-light.svg" width="16" height="16" alt=""></picture> [OpenAI API](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai) | Latency and errors, tokens and cost per request, debugging bad answers |
| <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/anthropic-dark.svg"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/anthropic-light.svg" width="16" height="16" alt=""></picture> [Anthropic API](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/anthropic) | Latency and errors, tokens and cost per request, debugging bad answers |
| <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/openai-dark.svg"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/openai-light.svg" width="16" height="16" alt=""></picture> [OpenAI Agents SDK](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/openai_agents) | Agent runs and delegation, tool calls, finding the step that failed |
| <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/claude-dark.svg"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/claude-light.svg" width="16" height="16" alt=""></picture> [Claude Agent SDK](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_agents) | Agent runs and delegation, tool calls, finding the step that failed |
| <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/claude-dark.svg"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/claude-light.svg" width="16" height="16" alt=""></picture> [Claude Code](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/claude_code) | Token and cost tracking per developer, project and session; expensive sessions and models |
| <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/openai-dark.svg"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/openai-light.svg" width="16" height="16" alt=""></picture> [Codex CLI](https://github.com/Anosys-AI/anosys-sdk/tree/main/packages/python/codex) | Token and cost tracking per developer, project and session; expensive sessions and models |
| <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/google-dark.svg"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/logos/google-light.svg" width="16" height="16" alt=""></picture> [Antigravity](https://github.com/Anosys-AI/anosys-sdk/blob/main/ANTIGRAVITY.md) | Agent activity, tool calls and commands, session time |

Every integration is available for Python and JavaScript. Not using these? Send data with OpenTelemetry (OTLP/HTTP or the Collector), the REST API, JavaScript tracking, image pixels or file upload; [Integration options](https://console.anosys.ai/collect/integrationoptions) gives you the key for each.

## Privacy by default

- **You choose what is sent:** `off`, `metadata` (ids, timing, models, tokens and cost) or `full` (prompts and responses too).
- **Coding tools send metadata only** until each user opts in to full collection and accepts the [data collection policy](https://github.com/Anosys-AI/anosys-sdk/blob/main/PRIVACY.md).
- **Projects can lower collection, never raise it**, and nothing overrides a user's choice to turn it down.
- **Optional client-side encryption** of all content before it leaves your machine.

Read more in [content controls](https://github.com/Anosys-AI/anosys-sdk/blob/main/DATA_CONTROLS.md).

## Repositories

- [anosys-sdk](https://github.com/Anosys-AI/anosys-sdk): Python and JavaScript integrations, example notebooks and reference docs.
- [AnoSys-Demo-Customer](https://github.com/Anosys-AI/AnoSys-Demo-Customer): an agentic real-estate app that shows Anosys.ai in a working product.
- [anosys-logger-4-openai](https://github.com/Anosys-AI/anosys-logger-4-openai) and [anosys-logger-4-openai-agents](https://github.com/Anosys-AI/anosys-logger-4-openai-agents): earlier standalone loggers, replaced by anosys-sdk. Use anosys-sdk for new work.

Questions? Email [support@anosys.ai](mailto:support@anosys.ai). The SDK is licensed under [Apache 2.0](https://github.com/Anosys-AI/anosys-sdk/blob/main/LICENSE).

<img src="https://api.anosys.ai/trafficpixel/925fb3f78b04d5b9d5aded56b44410c9/a/ea8a7985c8f3/anosys.gif?cvs198=https://github.com/Anosys-AI" width="1" height="1" alt=""/>
