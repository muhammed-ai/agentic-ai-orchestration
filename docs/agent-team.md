# Agent team

A five-agent custom team defined in `.github/agents/`, designed to be orchestrated through the GitHub Copilot CLI.

| Agent | Role | Definition |
| --- | --- | --- |
| Orchestrator | Coordinates the build, breaks work into phases, delegates to specialists, and verifies the integrated result. | `.github/agents/orchestrator.agent.md` |
| Planner | Researches the codebase and requirements, identifies dependencies and edge cases, and produces the implementation plan. | `.github/agents/planner.agent.md` |
| Coder | Implements application logic, writes code, fixes bugs, and prepares runnable app support when needed. | `.github/agents/coder.agent.md` |
| Designer | Owns UI/UX, accessibility, information hierarchy, and visual polish. | `.github/agents/designer.agent.md` |
| Reviewer | Independently checks implemented work for correctness, security, accessibility, and edge cases. Reports issues; does not edit code. | `.github/agents/reviewer.agent.md` |

## Setup

Each agent definition has a `model:` field set to `TODO-set-your-model`. Replace it with a real model you have access to in the Copilot CLI before using the team.

## Flow

1. The **Orchestrator** receives your request.
1. It asks the **Planner** for an implementation plan.
1. It parses the plan into phases with explicit file ownership.
1. It delegates to the **Coder** and **Designer**, running non-overlapping work in parallel and dependent work sequentially.
1. It sends the finished work to the **Reviewer** for an independent check. If the Reviewer requests changes, the issues go back to the Coder or Designer and the work is re-reviewed.
1. It integrates the results and reports the final outcome.

The Reviewer is intentionally kept separate from the agents that produce the work, and has no `edit` access, so review stays an independent gate rather than a self-check.

## Git control

All agents leave git operations to you. They will not stage, commit, or push unless you explicitly ask.
