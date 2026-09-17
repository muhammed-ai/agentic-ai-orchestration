---
mode: agent
description: Scaffold a new specialist agent definition for the team.
---

# New agent

Create a new specialist agent definition under `.github/agents/`.

Ask me for, or infer from context:

- The agent's **name** and one-sentence **description**.
- The agent's **responsibilities** and where it fits alongside the Orchestrator, Planner, Coder, Designer, and Reviewer.
- The **tools** it needs (grant the minimum required).

Then:

1. Create `.github/agents/<name>.agent.md` with YAML front matter (`name`, `description`, `model: TODO-set-your-model`, `tools`) followed by a role statement and sections for principles and rules.
1. Match the structure, tone, and ordered-list style of the existing agent files.
1. Include a "Git control" section stating the agent will not stage, commit, or push unless the user explicitly asks.
1. Update `README.md` and `docs/agent-team.md` so the team roster and flow stay accurate.

Do not perform any git operations.
