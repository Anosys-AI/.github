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
  <a href="https://anosys.ai">Website</a> · <a href="https://anosys.ai/docs/">Documentation</a> · <a href="https://console.anosys.ai">Console</a> · <a href="https://github.com/Anosys-AI/anosys-sdk">SDK</a> · <a href="https://www.linkedin.com/company/anosys-ai/">LinkedIn</a> · <a href="https://x.com/AnosysAI">X</a> · <a href="https://www.youtube.com/@anosysai">YouTube</a>
</p>

<p align="center">
  <a href="https://anosys.ai/assets/img/console/trace-tree.webp"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/screenshots/trace-tree.webp" alt="Agent trace tree: agents, model calls, tool calls and handoffs" width="32%"></a>
  <a href="https://anosys.ai/assets/img/console/trace-timeline-agents.webp"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/screenshots/trace-timeline-agents.webp" alt="Agent trace timeline with the duration of each step" width="32%"></a>
  <a href="https://anosys.ai/assets/img/console/web-analytics-dashboard.webp"><img src="https://raw.githubusercontent.com/Anosys-AI/anosys-sdk/main/assets/screenshots/web-analytics-dashboard.webp" alt="Website analytics dashboard" width="32%"></a>
</p>
<p align="center"><sub>Agent trace tree · Trace timeline · Website analytics. Click to enlarge.</sub></p>

## Why Anosys.ai

AI systems rarely fail loudly. A request succeeds while the answer is wrong. An agent retries, loops and calls the same tool again, and the bill grows while the task stays unsolved. When something goes wrong, nobody can say why the agent did what it did. Your monitoring shows healthy services; your customers see failures.

Anosys.ai connects what your AI does with what it costs and what it means for your users and your business, so you can find what changed, fix it and prove the fix worked.

**How it works:** **ingest** AI traces, application data, user activity, costs and evaluations from any source → **correlate** them into one shared context → **explain** what changed and why → **act** with alerts, evaluations and automated pipelines → **improve**, and measure again.

## What you can do

- **Debug AI agents.** See every run as a trace tree: model calls, tool calls, handoffs, outputs, tokens and errors in order. The RCA report and the AI Assistant help you get from a bad run to its root cause. [Agent tracing](https://anosys.ai/docs/agent-tracing/)
- **Evaluate quality.** Score what your AI actually produced, not just whether it errored. Run evaluation templates on live traffic or on datasets, compare prompts and models with experiments, and keep automated judges honest with human review. [Evaluations](https://anosys.ai/docs/evals/)
- **Catch silent regressions.** Detect changes in behavior, quality, latency and spend even when nothing throws an error, and get alerted in Slack, email or a webhook with rules or AI-evaluated conditions. [Alerts](https://anosys.ai/docs/alerts/)
- **Understand AI spend.** Tokens, cache use and estimated cost by model, person, project and workflow, for your own apps and for coding tools like Claude Code, Codex and Antigravity. See what the spend produces, not just what it costs. [AI and coding spend](https://anosys.ai/docs/cost-intelligence/)
- **Optimize your agents in a feedback loop.** Turn what you find into improvements: spot wasted tokens, retry loops and expensive models, test a fix by comparing prompts or models in an experiment, then confirm on live traffic that quality went up and cost went down. Every change feeds back into the next round of monitoring and evaluation. [Evaluations and experiments](https://anosys.ai/docs/evals/)
- **Connect AI to users and outcomes.** Website and product analytics and business process monitoring sit next to your AI traces, joined by your own user and session IDs. [Product analytics](https://anosys.ai/docs/product-analytics/) · [Business processes](https://anosys.ai/docs/business-process-monitoring/)
- **Make it yours.** Start from dashboard templates or Auto-Insights, or build your own. Turn queries into reusable process units, and chain processing, evaluations and alerts into scheduled pipelines. [Dashboards](https://anosys.ai/docs/custom-dashboards/) · [Pipelines](https://anosys.ai/docs/custom-pipelines/)
- **Ask in plain language.** The AI Assistant answers questions about your data, such as "why did Claude Code spend go up yesterday?", and builds dashboard widgets for you. [AI Assistant](https://anosys.ai/docs/ai-assistant/)

## Get started

Create a free account in the [Console](https://console.anosys.ai) and get a key from [Integration options](https://console.anosys.ai/collect/integrationoptions). Then pick your starting point:

| Start here | What you get | Set up |
| --- | --- | --- |
| **Monitor LLM calls** in your app | Every OpenAI or Anthropic call with prompt, response, latency, tokens and cost | `pip install anosys-sdk-openai openai` or `pip install anosys-sdk-anthropic anthropic`, then `AnosysOpenAILogger()` or `AnosysAnthropicLogger()` at startup |
| **Debug AI agents** | Every run of the OpenAI Agents SDK or Claude Agent SDK as a trace of model calls, tool calls and handoffs | `pip install anosys-sdk-openai-agents` or `pip install anosys-sdk-claude-agents`, then one line at startup |
| **Track coding-assistant spend** | Tokens and cost of Claude Code, Codex and Antigravity by developer, project and model | `pip install anosys-claude-code && anosys-claude-code install` (likewise `anosys-codex`, `anosys-antigravity`) |
| **Website and product analytics** | Visitors, sessions, sources, clicks and Web Vitals, and signed-in users across sessions | One `<script>` tag in your site's footer |

Every SDK is also available for JavaScript (`npm install anosys-sdk-openai openai` and so on). The [SDK guide](https://github.com/Anosys-AI/anosys-sdk#get-started) has copy-paste examples for each path, and the [documentation](https://anosys.ai/docs/getting-started/) covers website analytics and sending any other data.

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
- **Optional encryption with your own key** of all content before it leaves your machine, plus redaction and alerts on sensitive data.

Read more in [security and data controls](https://anosys.ai/docs/data-encryption/) and the SDK's [content controls](https://github.com/Anosys-AI/anosys-sdk/blob/main/DATA_CONTROLS.md).

## Repositories

- [anosys-sdk](https://github.com/Anosys-AI/anosys-sdk): Python and JavaScript integrations, example notebooks and reference docs.

Questions? Email [support@anosys.ai](mailto:support@anosys.ai). The SDK is licensed under [Apache 2.0](https://github.com/Anosys-AI/anosys-sdk/blob/main/LICENSE).

<img src="https://api.anosys.ai/trafficpixel/925fb3f78b04d5b9d5aded56b44410c9/a/ea8a7985c8f3/anosys.gif?cvs198=https://github.com/Anosys-AI" width="1" height="1" alt=""/>
