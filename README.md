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
    ██╔═══╝ ██║╚██╔╝██║      uptime    400+ prs · 30+ prod repos · since dec '25
    ██║     ██║ ╚═╝ ██║      kernel    voice copilots, coding agents, event backbones
    ╚═╝     ╚═╝     ╚═╝      shell     claude code, codex, cursor
                             prev      salespatriot (yc w25) · sail · psu cs '25
```

Insurance has always run on agents. I build the new kind, at Harper (YC W25,
$47M Series A, Series B underway). Mine are Dumbly, the realtime voice copilot our
intake operators live in, and DaVinci, a background coding agent that drives work
from research through integration testing, plus the pipelines and evals underneath
both. The models were never the bottleneck. Getting an agent to behave when a
carrier sends a scanned PDF sideways at 4:55pm on a Friday, that's the job.

## how i work

- zero to one is where I'm useful. hand me a fuzzy problem and a customer who's annoyed,
  not a spec
- I build for someone's actual workflow, then sit next to them and watch where it breaks.
  the watching is the part people skip
- duct tape first, Temporal second. the trick is knowing which week you're in

## shipping at harper

| system | built with | what happened |
|---|---|---|
| Dumbly — realtime intake copilot | OpenAI Realtime API, Electron, packet-recommendation rules engine | 20+ operators, 300-400 intakes/day, manual intake down ~70% |
| DaVinci — background coding agent | ECS/Fargate, SQS FIFO, Step Functions, Postgres | research → plan → execute → integration-test; capacity-gated executors that root-cause failures (code vs test vs env) before retrying |
| lead lifecycle pipeline | Temporal (python + go workers), Postgres | raw lead → qualified opportunity → submission handoff. dual-write migrations, typed backfills, no downtime cutover |
| event backbone | schema registry, go SDK, NATS | event contracts for 5+ services. shipping a schema change through every consumer in one day |
| growth attribution stack | GCLID/msclkid capture, offline conversions, Customer.io | ad-click to closed-policy attribution; lifecycle campaigns fired off production events |
| reliability layer | otel, logfire, feature flags | fail-closed guards on anything customer-facing. about 50 PRs nobody sees, which is the point |

## open source

five open PRs and counting, all upstream of things I run in prod:

- [anthropics/claude-agent-sdk-python #1087](https://github.com/anthropics/claude-agent-sdk-python/pull/1087) —
  list-form system prompts crashed deep in the subprocess transport with a cryptic
  AttributeError, after the money was already spent. now fails fast at construction
  with an error that tells you what to do instead
- [livekit/agents #6321](https://github.com/livekit/agents/pull/6321) — a stored tool call
  with unparseable arguments could crash every later turn of a voice agent. fix + tests
  for the Anthropic/Google/AWS formatters
- [inspect_ai #4418](https://github.com/UKGovernmentBEIS/inspect_ai/pull/4418) — hidden
  states were silently dropped from eval logs as `None`. now they survive serialization
- [simonw/datasette #2826](https://github.com/simonw/datasette/pull/2826) — text and
  composite primary keys created through the JSON API were silently nullable, producing
  rows you can't view or delete. now NOT NULL at creation
- [python-attrs/attrs #1584](https://github.com/python-attrs/attrs/pull/1584) —
  include/exclude filters matched attributes by equality, so excluding one class's field
  could silently drop an identical field on an unrelated class. now matched by identity

**mine:**

| project | one-liner |
|---|---|
| [DaVinci case study](https://pranavmishra.app/case-studies/davinci) | how the background coding agent works: the executor loop, the capacity state machine, and why the human gates are an architecture |
| [autogen-distributed-agents](https://github.com/PranavMishra28/autogen-distributed-agents) | 20 concurrent agents on a gRPC runtime critiquing each other's ideas |
| [langgraph-sidekick-assistant](https://github.com/PranavMishra28/langgraph-sidekick-assistant) | worker/evaluator loop with memory, browsing, and a python REPL |

**contributing next:** [openai-agents-python](https://github.com/openai/openai-agents-python) ·
[pydantic-ai](https://github.com/pydantic/pydantic-ai) ·
[semantic-conventions-genai](https://github.com/open-telemetry/semantic-conventions-genai)

## writing

- [Agents need a nervous system, not a bigger brain](https://pranavmishra.app/blog/agents-need-a-nervous-system) —
  the next gains come from durable execution and replayable state, not bigger models
- [When both sides of the API are agents](https://pranavmishra.app/blog/when-both-sides-of-the-api-are-agents) —
  B2B software when your customer's workflows are agentic too
- [Human-in-the-loop is an architecture, not a checkbox](https://pranavmishra.app/blog/human-in-the-loop-is-an-architecture) —
  escalation ladders, fail-closed gates, and when the human is the product

## reading

| paper | notes |
|---|---|
| [τ-bench](https://arxiv.org/abs/2406.12045) | agents following domain policy with a human in the loop. closest thing to a benchmark of my day job |
| [ReAct](https://arxiv.org/abs/2210.03629) | still the skeleton under most agent loops, including mine |
| [Reflexion](https://arxiv.org/abs/2303.11366) | self-critique as memory. cheap and it works |
| [CoALA](https://arxiv.org/abs/2309.02427) | a map of agent architectures. I disagree with parts, which is why I keep rereading it |
| [SWE-bench](https://arxiv.org/abs/2310.06770) | made coding agents measurable |
| [Generative Agents](https://arxiv.org/abs/2304.03442) | the smallville paper. memory and routines for 25 agents in a toy town |

## stack

```yaml
# toolchain.yaml
langs:         [python, typescript, go, java, sql]
agents:        [claude agent sdk + mcp, langgraph, autogen, openai realtime, evals]
voice:         [openai realtime api, twilio, elevenlabs]
backbone:      [temporal, nats, trigger.dev, n8n, rest + graphql]
data:          [postgres + pgvector, supabase, qdrant, chroma, mongodb]
frontend:      [react, react native, electron, sveltekit, next.js]
infra:         [aws, gcp, cloudflare, docker, k8s, helm, argocd, github actions]
observability: [otel, logfire, posthog, grafana]
daily_drivers: [claude code, codex, cursor]
```

## numbers

<div align="center">
<a href="https://github.com/PranavMishra28"><img src="https://github-readme-activity-graph.vercel.app/graph?username=PranavMishra28&theme=tokyo-night&hide_border=true&area=true&custom_title=contributions%2C%20last%2030%20days" width="97%"></a>

<sub>most of my work lives in private org repos. the graph is what leaks through; the five PRs above are the part that doesn't have to.</sub>
</div>

---

<div align="center"><code>$ curl -s pranavmishra.app | grep -i "building"</code></div>
