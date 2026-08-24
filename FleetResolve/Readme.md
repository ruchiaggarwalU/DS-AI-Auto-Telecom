# FleetResolve — AI-Powered Fleet Issue Investigation

## The Problem

Fleet operators spend too much time manually triaging and investigating fleet issues instead of resolving them. As fleets grow, operators must piece together device state, incident history, user context, and operational knowledge before deciding what needs attention and what to do next.

## The Solution

FleetResolve is an agentic fleet operations prototype designed to reduce mean time to resolution (MTTR) and lower fleet operating costs by shifting investigation work to an AI agent.

The agent gathers relevant context, investigates issues across available operational data, synthesizes the evidence, and produces a recommendation for the operator. Deterministic policy and validation constrain the recommendation, while consequential decisions remain with a human.

## Live Demo

**View the Live Prototype:** [ADD LIVE DEMO URL]

## How It Works

1. **Fleet Signal:** A device issue enters the investigation workflow.
2. **Agent Investigation:** The AI agent determines what information it needs and retrieves relevant device state, user context, and incident history.
3. **Evidence Synthesis:** The agent combines retrieved evidence with operational knowledge to understand the issue.
4. **Policy & Recommendation:** Decision policy constrains what the agent can recommend.
5. **Validation:** The recommendation is checked for unsupported operational details.
6. **Human Resolution:** Valid recommendations are surfaced to the operator; consequential actions remain subject to human approval.

## The Agentic Product Innovation

Instead of encoding every possible investigation path as deterministic rules, **FleetResolve uses AI as an adaptive investigation layer**.

The agent determines how to investigate based on what it discovers, while deterministic policy defines the boundaries and humans retain control over consequential decisions.

> **AI investigates. Policy constrains. Humans decide.**

## System Architecture

```text
┌────────────────────────┐      ┌────────────────────────┐      ┌────────────────────────┐
│     Fleet Signals      │ ───> │   AI Investigation     │ ───> │    Recommendation      │
│ Device State           │      │ Issue Understanding    │      │ Evidence + Policy      │
│ Alerts & Events        │      │ Evidence Retrieval     │      │ Next Best Action       │
│ Incident History       │      │ Reasoning & Analysis   │      │ Confidence / Impact    │
│ User Context           │      │ Recommendation         │      │                        │
└────────────────────────┘      └───────────┬────────────┘      └───────────┬────────────┘
                                            │                               │
                                            ▼                               ▼
                                  ┌────────────────────────┐      ┌────────────────────────┐
                                  │ Knowledge & Policy     │      │ Human-in-the-Loop      │
                                  │ Operational Knowledge  │      │ Operator Review        │
                                  │ Decision Policy        │      │ Approve / Modify /     │
                                  │ Guardrails             │      │ Reject / Resolve       │
                                  └────────────────────────┘      └────────────────────────┘
```

## Prototype Artifacts

- **Live Demo:** [ADD LIVE DEMO URL]
- **Notebook:** [FleetResolve_Agent.ipynb](./FleetResolve_Agent.ipynb)
- **PRFAQ:** [PRFAQ.md](./PRFAQ.md)
- **Slides:** [View slides](./slides/)

## Tech Stack

- **Agent / LLM:** LangChain with Groq integration
- **Model:** `openai/gpt-oss-120b`
- **Backend:** FastAPI with Uvicorn
- **Prototype Environment:** Python / Google Colab
- **Interface:** Browser-based FleetResolve UI
- **Controls:** Deterministic decision policy, evidence validation, and human-in-the-loop guardrails

## Running the Prototype

1. Open `FleetResolve_Agent.ipynb`.
2. Add `GROQ_API_KEY` to Google Colab Secrets.
3. Run the notebook cells in order.
4. Start the FastAPI backend and browser UI from the notebook.

## Prototype Scope

FleetResolve currently uses synthetic fleet data and demonstrates the concept-to-prototype agent workflow. It is not a production fleet-management integration and does not autonomously execute consequential fleet actions.

