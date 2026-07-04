<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://readme-typing-svg.demolab.com?font=Press+Start+2P&size=20&pause=1000&color=79C0FF&center=true&vCenter=true&width=800&height=70&lines=%24+whoami;pranav+mishra;fde+%40+harper+(yc+w25);agents+in+prod%2C+not+demos">
  <img alt="pranav mishra" src="https://readme-typing-svg.demolab.com?font=Press+Start+2P&size=20&pause=1000&color=0969DA&center=true&vCenter=true&width=800&height=70&lines=%24+whoami;pranav+mishra;fde+%40+harper+(yc+w25);agents+in+prod%2C+not+demos">
</picture>

<a href="https://pranavmishra.app"><img src="https://img.shields.io/badge/portfolio-pranavmishra.app-58a6ff?style=flat-square"></a>
<a href="https://linkedin.com/in/pm28"><img src="https://img.shields.io/badge/linkedin-pm28-58a6ff?style=flat-square"></a>
<a href="https://x.com/pranavmishra28"><img src="https://img.shields.io/badge/x-@pranavmishra28-58a6ff?style=flat-square"></a>
<img src="https://komarev.com/ghpvc/?username=PranavMishra28&style=flat-square&color=58a6ff&label=visitors&abbreviated=true">
</div>

```text
pranav@harper ~ $ neofetch

    ██████╗ ███╗   ███╗      pranav @ san francisco
    ██╔══██╗████╗ ████║      ─────────────────────────────────────
    ██████╔╝██╔████╔██║      role      forward deployed engineer, harper (yc w25)
    ██╔═══╝ ██║╚██╔╝██║      uptime    400+ prs · 30+ prod repos · last 7 months
    ██║     ██║ ╚═╝ ██║      kernel    voice copilots, temporal pipelines, event backbones
    ╚═╝     ╚═╝     ╚═╝      shell     claude code, cursor
                             prev      salespatriot (yc w25) · sail · psu cs '25
```

I build AI agents for commercial insurance and my job is making them survive contact
with reality: real operators, real policies, real money attached. Live transcription
copilots, lead pipelines on Temporal, an event schema layer that five services depend on,
and all the evals, guardrails and tracing that keep it honest. The thing I keep relearning
is that the model is never the hard part. The last mile is.

## how i operate

- zero to one is the fun part. give me a fuzzy problem and a customer, not a spec
- living room products: i build for people's actual workflow, then sit next to them and watch where it breaks
- scrappy first, durable second. ship the duct tape version this week, replace it with Temporal next week
- full stack means full stack: pixels, APIs, workflows, schemas, dashboards, and the pager when it breaks

## shipping at harper

| system | what it does |
|---|---|
| realtime intake copilot | desktop voice agent for live transcription into structured insurance intake. cut manual intake ~70% |
| lead lifecycle pipeline | Temporal workflows (python/go) from raw lead to qualified opportunity to submission handoff. zero-downtime migrations, typed backfills |
| event backbone | schema registry + go SDK powering event contracts across 5+ services. same-day cross-repo rollout trains |
| agent skills platform | orchestrated customer-touchpoint skills: docs, onboarding, form-fill |
| reliability layer | otel tracing, feature flags, fail-closed guards, security hardening. the unglamorous 50 prs that make agents trustworthy |
| document automation | ACORD generation and PDF pipelines, AcroForm coordinate hell included |

## open source

**mine:**

| repo | one-liner |
|---|---|
| [autogen-distributed-agents](https://github.com/PranavMishra28/autogen-distributed-agents) | 20 concurrent agents on a gRPC runtime with peer critique |
| [langgraph-sidekick-assistant](https://github.com/PranavMishra28/langgraph-sidekick-assistant) | worker/evaluator loop with persistent memory, browsing, and a python REPL |
| [genai-discord-pipeline](https://github.com/PranavMishra28/genai-discord-pipeline) | discord → embeddings → RAG Q&A (n8n, flask, chroma) |

**contributing next** (agent infra I run in prod and want to give back to):

[modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) ·
[anthropics/skills](https://github.com/anthropics/skills) ·
[UKGovernmentBEIS/inspect_ai](https://github.com/UKGovernmentBEIS/inspect_ai) ·
[promptfoo/promptfoo](https://github.com/promptfoo/promptfoo) ·
[langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) ·
[temporalio/sdk-python](https://github.com/temporalio/sdk-python)

## reading

agent papers I keep coming back to:

| paper | why it matters to me |
|---|---|
| [ReAct](https://arxiv.org/abs/2210.03629) | reasoning + acting interleaved. still the backbone of every agent loop I ship |
| [Reflexion](https://arxiv.org/abs/2303.11366) | self-critique as memory. the cheapest reliability win there is |
| [τ-bench](https://arxiv.org/abs/2406.12045) | agents following domain rules with humans in the loop. basically my day job, as a benchmark |
| [SWE-bench](https://arxiv.org/abs/2310.06770) | the benchmark that made coding agents honest |
| [CoALA](https://arxiv.org/abs/2309.02427) | cognitive architectures for language agents. a map for everything above |
| [Generative Agents](https://arxiv.org/abs/2304.03442) | the smallville paper. memory + routines, before it was cool |

## writing

- coming soon

## stack

```yaml
# toolchain.yaml
langs:         [python, typescript, go, java, sql]
agents:        [claude + mcp, langgraph, autogen, crewai, openai realtime, rag + evals]
voice:         [openai realtime api, twilio, elevenlabs]
backbone:      [temporal, nats, trigger.dev, n8n, rest + graphql]
data:          [postgres + pgvector, supabase, qdrant, chroma, mongodb]
frontend:      [react, react native, electron, sveltekit, next.js, vue]
infra:         [aws, gcp, cloudflare, docker, k8s, helm, argocd, github actions]
observability: [otel, logfire, posthog, grafana]
daily_drivers: [claude code, codex, cursor]
```

## numbers

<div align="center">
<a href="https://github.com/PranavMishra28"><img src="https://github-readme-activity-graph.vercel.app/graph?username=PranavMishra28&theme=tokyo-night&hide_border=true&area=true&custom_title=contributions%2C%20last%2030%20days" width="97%"></a>

<sub>most of my work lives in private org repos. the graph above is what leaks through.</sub>
</div>

---

<div align="center"><code>$ curl -s pranavmishra.app | grep -i "building"</code></div>
