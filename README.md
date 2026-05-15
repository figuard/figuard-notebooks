# FiGuard Notebooks

Pre-built Colab notebooks for every FiGuard configuration pattern. Each notebook runs against the live sandbox (`sandbox.figuard.io`, key `sb_live_demo`) — no signup, no local setup required.

## Notebooks

| Notebook | Pattern | Open |
|---|---|---|
| `monetary-single-agent.ipynb` | Money budget · single agent | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/monetary-single-agent.ipynb) |
| `monetary-with-categories.ipynb` | Money budget · per-category limits | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/monetary-with-categories.ipynb) |
| `monetary-fleet.ipynb` | Money budget · fleet + delegation tokens | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/monetary-fleet.ipynb) |
| `tokens-single-agent.ipynb` | Token budget · single agent | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/tokens-single-agent.ipynb) |
| `tokens-with-categories.ipynb` | Token budget · per-model limits | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/tokens-with-categories.ipynb) |
| `api-calls-single-agent.ipynb` | API call budget · single agent | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/api-calls-single-agent.ipynb) |
| `langchain-shopping-agent.ipynb` | LangChain callback integration | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/langchain-shopping-agent.ipynb) |
| `crewai-research-fleet.ipynb` | CrewAI crew guard integration | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/crewai-research-fleet.ipynb) |
| `openai-agents-travel-booking.ipynb` | OpenAI Agents SDK decorator | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/figuard/figuard-notebooks/blob/main/openai-agents-travel-booking.ipynb) |

## What each notebook does

Three cells, nothing more:

1. **Install** — `!pip install figuard -q`
2. **Create budget** — connects to the sandbox, creates a budget with your pattern's configuration
3. **Authorize and deny** — runs a successful authorization, confirms it, then shows a denied attempt. Final line links to `https://sandbox.figuard.io/ui` where you can see the spend tree.

## Sandbox

- **URL**: `https://sandbox.figuard.io`
- **Key**: `sb_live_demo` (read-only, shared, pre-seeded)
- **Dashboard**: `https://sandbox.figuard.io/ui`

The sandbox resets periodically. Your session data appears in the dashboard immediately after running a notebook.
