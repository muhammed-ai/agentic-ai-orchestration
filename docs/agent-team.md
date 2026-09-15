# Agent team

A four-agent custom team defined in `.github/agents/`, designed to be orchestrated through the GitHub Copilot CLI.

| Agent | Role | Definition |
| --- | --- | --- |
| Orchestrator | Coordinates the build, breaks work into phases, delegates to specialists, and verifies the integrated result. | `.github/agents/orchestrator.agent.md` |
| Planner | Researches the codebase and requirements, identifies dependencies and edge cases, and produces the implementation plan. | `.github/agents/planner.agent.md` |
| Coder | Implements application logic, writes code, fixes bugs, and prepares runnable app support when needed. | `.github/agents/coder.agent.md` |
| Designer | Owns UI/UX, accessibility, information hierarchy, and visual polish. | `.github/agents/designer.agent.md` |

## Setup

Each agent definition has a `model:` field set to `TODO-set-your-model`. Replace it with a real model you have access to in the Copilot CLI before using the team.

## Flow

1. The **Orchestrator** receives your request.
1. It asks the **Planner** for an implementation plan.
1. It parses the plan into phases with explicit file ownership.
1. It delegates to the **Coder** and **Designer**, running non-overlapping work in parallel and dependent work sequentially.
1. It integrates the results and reports the final outcome.

## Git control

All agents leave git operations to you. They will not stage, commit, or push unless you explicitly ask.
