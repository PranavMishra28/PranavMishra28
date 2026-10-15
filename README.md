<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://readme-typing-svg.demolab.com?font=Press+Start+2P&size=20&pause=1000&color=79C0FF&center=true&vCenter=true&width=800&height=70&lines=%24+whoami;pranav+mishra;fde+%40+harper+(yc+w25);voice+agents+that+take+the+call;a+coding+agent+on+one+laptop;receipts+%3E+demos">
  <img alt="pranav mishra" src="https://readme-typing-svg.demolab.com?font=Press+Start+2P&size=20&pause=1000&color=0969DA&center=true&vCenter=true&width=800&height=70&lines=%24+whoami;pranav+mishra;fde+%40+harper+(yc+w25);voice+agents+that+take+the+call;a+coding+agent+on+one+laptop;receipts+%3E+demos">
</picture>

<a href="https://pranavmishra.app"><img src="https://img.shields.io/badge/portfolio-pranavmishra.app-58a6ff?style=flat-square"></a>
<a href="https://linkedin.com/in/pm28"><img src="https://img.shields.io/badge/linkedin-pm28-58a6ff?style=flat-square"></a>
<a href="https://x.com/pranavmishra28"><img src="https://img.shields.io/badge/x-@pranavmishra28-58a6ff?style=flat-square"></a>
<a href="https://pranavmishra.app/feed.xml"><img src="https://img.shields.io/badge/rss-writing-58a6ff?style=flat-square"></a>
<img src="https://komarev.com/ghpvc/?username=PranavMishra28&style=flat-square&color=58a6ff&label=visitors&abbreviated=true">
</div>

```text
pranav@harper ~ $ neofetch

    ██████╗ ███╗   ███╗      pranav @ san francisco
    ██╔══██╗████╗ ████║      ─────────────────────────────────────────────
    ██████╔╝██╔████╔██║      role      forward deployed engineer, harper (yc w25)
    ██╔═══╝ ██║╚██╔╝██║      uptime    1,100+ prs · 900+ merged · 60+ repos since oct '25
    ██║     ██║ ╚═╝ ██║      kernel    voice agents, local coding agents, agent reliability
    ╚═╝     ╚═╝     ╚═╝      upstream  merged into openai-agents-python, livekit/agents, inspect_ai
                             shell     claude code, codex, cursor, opencode
                             prev      salespatriot (yc w25) · sail · psu cs '25
```

Insurance has always run on agents. I build the new kind, at [Harper](https://www.harperinsure.com)
(YC W25, $47M across Seed and Series A). First an intake copilot our operators live in, now a voice
agent that answers the phone by itself and turns the call into an insurance application. The models
were never the bottleneck. Getting an agent to behave when a caller says *"don't email and text"*, or
a carrier sends a scanned PDF sideways at 4:55pm on a Friday, that's the job.

On my own time I build the same thing at a different scale: a coding agent that runs on one laptop,
and the benchmark rig that decides when it's allowed to claim it's good.

## now

```diff
+ kryn        v1 shipped. next: seal a holdout, climb the research ladder toward frontier-adjacent on a 9B model
+ voice       live calls: realtime model talks, deepgram listens, code owns hang-ups, transfers, confirmations
+ irrevon     waiting on a preregistration freeze before the first confirmatory benchmark run
+ upstream    4 merged, 7 in review across the openai, anthropic, livekit and python ecosystems
```

## shipping at harper

| system | built with | what happened |
|---|---|---|
| voice intake agent | LiveKit, OpenAI Realtime, Deepgram Nova-3, SIP | takes intake calls alone. I own how calls end (hang-up, transfer, holds) and the confirmation loop where callers fix their own details before anything is filed. [write-up](https://pranavmishra.app/case-studies/voice-intake-agent) |
| Dumbly: realtime intake copilot | OpenAI Realtime API, Electron, packet-recommendation rules engine | 20+ operators, 300-400 intakes/day, manual intake down ~70% |
| lead lifecycle pipeline | Temporal (python + go workers), Postgres | raw lead → qualified opportunity → submission handoff. dual-write migrations, typed backfills, no-downtime cutover |
| event backbone | schema registry, go SDK, NATS | event contracts for 5+ services. a schema change through every consumer in one day |
| growth attribution stack | GCLID/msclkid capture, offline conversions, Customer.io | ad-click to closed-policy attribution; lifecycle campaigns fired off production events |
| reliability layer | otel, logfire, feature flags | fail-closed guards on anything customer-facing. about 50 PRs nobody sees, which is the point |

## built in the open

| project | what it is | status |
|---|---|---|
| [**KRYN**](https://github.com/PranavMishra28/kryn) | local coding workspace for Apple Silicon: OpenCode + a guarded Qwen 9B on oMLX, plus a preregistered benchmark rig (matched pairs, hidden graders, SWE-bench + Terminal-Bench subsets). [write-up](https://pranavmishra.app/case-studies/kryn) | ![release](https://img.shields.io/github/v/release/PranavMishra28/kryn?style=flat-square&label=&color=58a6ff) supervised |
| [**Irrevon**](https://github.com/PranavMishra28/irrevon) | reconciliation for irreversible agent actions: an identity the model can't regenerate, "ambiguous" as a real state, settlement from the destination's own evidence. [write-up](https://pranavmishra.app/case-studies/irrevon) | ![pypi](https://img.shields.io/pypi/v/irrevon?style=flat-square&label=&color=58a6ff) alpha |
| [**EONFOLK**](https://github.com/PranavMishra28/eonfolk) | deterministic civilization game where only one layer can write the world. models propose, Reality decides, a Chronicle that can't overclaim. [write-up](https://pranavmishra.app/case-studies/eonfolk) | pre-alpha |
| [**Interlock**](https://github.com/PranavMishra28/interlock) | turns a decision made in passing in Slack into one owner-approved, fail-closed action with a checkable receipt | hackathon build |

## upstream

| repo | pr | |
|---|---|---|
| [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | [record model-call failures on the provider's own span](https://github.com/openai/openai-agents-python/pull/4143) | ![merged](https://img.shields.io/badge/merged-8957e5?style=flat-square) |
| [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | [cancel sibling env resolvers when one fails](https://github.com/openai/openai-agents-python/pull/4195) | ![merged](https://img.shields.io/badge/merged-8957e5?style=flat-square) |
| [livekit/agents](https://github.com/livekit/agents) | [tolerate unparseable stored tool-call arguments](https://github.com/livekit/agents/pull/6321) | ![merged](https://img.shields.io/badge/merged-8957e5?style=flat-square) |
| [UKGovernmentBEIS/inspect_ai](https://github.com/UKGovernmentBEIS/inspect_ai) | [fix hidden_states recorded as null in eval logs](https://github.com/UKGovernmentBEIS/inspect_ai/pull/4418) | ![merged](https://img.shields.io/badge/merged-8957e5?style=flat-square) |

<sub>in review: <a href="https://github.com/anthropics/anthropic-sdk-python/pull/1750">anthropic-sdk-python#1750</a> · <a href="https://github.com/anthropics/anthropic-sdk-python/pull/1751">#1751</a> · <a href="https://github.com/anthropics/claude-agent-sdk-python/pull/1087">claude-agent-sdk-python#1087</a> · <a href="https://github.com/openai/openai-python/pull/3505">openai-python#3505</a> · <a href="https://github.com/openai/gpt-oss/pull/252">gpt-oss#252</a> · <a href="https://github.com/simonw/datasette/pull/2826">datasette#2826</a> · <a href="https://github.com/python-attrs/attrs/pull/1584">attrs#1584</a> · <a href="https://pranavmishra.app/projects">all of it</a></sub>

## writing

<!-- BLOG-POST-LIST:START -->
- [A voice agent that takes the call alone](https://pranavmishra.app/case-studies/voice-intake-agent)
- [The model doesn't get to write history](https://pranavmishra.app/case-studies/eonfolk)
- [Chasing frontier-level coding on one laptop](https://pranavmishra.app/case-studies/kryn)
- [The destination is the only witness](https://pranavmishra.app/case-studies/irrevon)
- [Agents need a nervous system, not a bigger brain](https://pranavmishra.app/blog/agents-need-a-nervous-system)
<!-- BLOG-POST-LIST:END -->

<sub>more at <a href="https://pranavmishra.app/writing">pranavmishra.app/writing</a> · <a href="https://pranavmishra.app/feed.xml">rss</a></sub>

## reading

| paper | notes |
|---|---|
| [τ-bench](https://arxiv.org/abs/2406.12045) | agents following domain policy with a human in the loop. closest thing to a benchmark of my day job |
| [SWE-bench](https://arxiv.org/abs/2310.06770) | made coding agents measurable. KRYN's external subset runs on its official evaluator |
| [Measuring AI ability to complete long software tasks](https://arxiv.org/abs/2503.14499) | METR's time horizons. how I want to plot KRYN's long-session runs |
| [ReAct](https://arxiv.org/abs/2210.03629) | still the skeleton under most agent loops, including mine |
| [Reflexion](https://arxiv.org/abs/2303.11366) | self-critique as memory. cheap, and on a 9B model, harder than it looks |
| [CoALA](https://arxiv.org/abs/2309.02427) | a map of agent architectures. I disagree with parts, which is why I keep rereading it |

## stack

```yaml
# toolchain.yaml
langs:         [python, typescript, go, sql]
agents:        [claude agent sdk + mcp, openai agents sdk, langgraph, evals]
voice:         [livekit agents, openai realtime, deepgram nova-3, twilio sip]
local:         [opencode, oMLX, mlx, qwen]
backbone:      [temporal, nats, postgres + pgvector, supabase]
frontend:      [react, next.js, electron, react native]
infra:         [aws ecs, gcp, cloudflare, docker, github actions]
observability: [otel, logfire, posthog, grafana]
daily_drivers: [claude code, codex, cursor]
```

## numbers

<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=PranavMishra28&theme=tokyonight&hide_border=true&background=00000000">
  <img alt="contribution streak" src="https://streak-stats.demolab.com?user=PranavMishra28&theme=default&hide_border=true&background=00000000">
</picture>

<img alt="contribution calendar" src="https://ghchart.rshah.org/0969da/PranavMishra28" width="97%">
<sub> most of my work lives in private org repos. the graph is what leaks through; the upstream PRs above are the part that doesn't have to. </sub>
</div>

---

<div align="center"><code>$ curl -s pranavmishra.app/llms.txt | head -3</code></div>
