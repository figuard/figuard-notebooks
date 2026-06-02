<img src="docs/logo.svg" alt="FiGuard" height="44" />

Pre-built Colab notebooks for every FiGuard pattern. Each runs against the live sandbox — no signup, no local setup. Click **Open in Colab**, then **Runtime → Run all**.

## Budget types

| Notebook | What it demonstrates | Open |
|---|---|---|
| `monetary-single-agent.ipynb` | Single agent with a $500 spend cap — authorize → confirm → deny lifecycle plus velocity controls and shadow mode | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/monetary-single-agent.ipynb) |
| `monetary-with-categories.ipynb` | Per-category allocations ($300 flights / $200 hotels) — spending in the wrong category is denied | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/monetary-with-categories.ipynb) |
| `monetary-fleet.ipynb` | Multi-agent fleet with delegation tokens — each sub-agent gets a hard cap; one runaway doesn't affect the others | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/monetary-fleet.ipynb) |
| `tokens-single-agent.ipynb` | Token budget that caps LLM token usage instead of dollars — same authorize/confirm/deny lifecycle | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/tokens-single-agent.ipynb) |
| `tokens-with-categories.ipynb` | Token budget with per-model limits — GPT-4o and Claude get separate token pools | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/tokens-with-categories.ipynb) |
| `api-calls-single-agent.ipynb` | API call budget that caps external data-source requests — useful when each call costs money | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/api-calls-single-agent.ipynb) |

## Framework integrations

| Notebook | What it demonstrates | Open |
|---|---|---|
| `openai-agents-travel-booking.ipynb` | OpenAI Agents SDK — `@guarded_function_tool` wraps a flight-booking tool; shows authorized and denied calls | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/openai-agents-travel-booking.ipynb) |
| `langchain-shopping-agent.ipynb` | LangChain — `FiGuardCallbackHandler` in the callback stack gates every tool call before it executes | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/langchain-shopping-agent.ipynb) |
| `crewai-research-fleet.ipynb` | CrewAI — `FiGuardCrewGuard` wraps crew tools; Part 1 shows a single agent, Part 2 shows a fleet with delegation tokens | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/crewai-research-fleet.ipynb) |

## Agent incident playbook

Real-world failure modes and how FiGuard stops them.

| Notebook | What it demonstrates | Open |
|---|---|---|
| `agent-incidents/01_infinite_loop.ipynb` | Agent stuck in a loop makes hundreds of calls — budget exhaustion stops it automatically | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/agent-incidents/01_infinite_loop.ipynb) |
| `agent-incidents/02_duplicate_payment.ipynb` | Retry logic fires the same payment twice — idempotency key makes the second request a no-op | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/agent-incidents/02_duplicate_payment.ipynb) |
| `agent-incidents/03_concurrent_overspend.ipynb` | Two agents race to spend the same budget — FiGuard serializes authorization so only one wins | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/agent-incidents/03_concurrent_overspend.ipynb) |
| `agent-incidents/04_rogue_subagent_fleet.ipynb` | One sub-agent in a fleet goes rogue — delegation token caps it without disrupting the other agents | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/agent-incidents/04_rogue_subagent_fleet.ipynb) |
| `agent-incidents/05_category_violation.ipynb` | Agent tries to spend outside its allowed category — category enforcement blocks the attempt | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/agent-incidents/05_category_violation.ipynb) |

## Advanced framework scenarios

Side-by-side before/after: the same agent workflow without and with FiGuard.

| Notebook | What it demonstrates | Open |
|---|---|---|
| `framework-scenarios/01_langchain_payment_retry.ipynb` | LangChain payment retry loop — without FiGuard a bug retries indefinitely; with FiGuard the retry budget stops it | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/framework-scenarios/01_langchain_payment_retry.ipynb) |
| `framework-scenarios/02_langgraph_research_loop.ipynb` | LangGraph research loop — each graph iteration is pre-authorized; the loop stops the moment the budget is exhausted | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/framework-scenarios/02_langgraph_research_loop.ipynb) |
| `framework-scenarios/03_langgraph_supervisor_fleet.ipynb` | LangGraph supervisor with three sub-agents — delegation tokens give each agent a hard cap; the rogue researcher can't drain the fleet | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/framework-scenarios/03_langgraph_supervisor_fleet.ipynb) |
| `framework-scenarios/04_crewai_parallel_crew.ipynb` | CrewAI parallel crew — a runaway market researcher is capped at $2; the financial analyst and report writer complete unaffected | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/framework-scenarios/04_crewai_parallel_crew.ipynb) |

## Sandbox

All notebooks connect to the shared demo environment — no account needed.

- **Key**: `sb_live_demo` (built into the SDK default)
- **Dashboard**: [figuard-sandbox-g1ha.onrender.com/ui](https://figuard-sandbox-g1ha.onrender.com/ui)

Each notebook prints a direct link to its own budget in the dashboard after running, so you can inspect the spend tree without searching.

The sandbox resets periodically. No uptime SLA — for production use, [self-host](https://github.com/figuard/figuard-core#self-hosting).
