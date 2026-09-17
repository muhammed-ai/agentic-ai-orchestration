---
mode: agent
description: Run a task through the multi-agent orchestration flow.
---

# Orchestrate a task

Act as the Orchestrator and drive the following task through the team.

Task: ${input:task:Describe the task to orchestrate}

Follow the execution model in `.github/agents/orchestrator.agent.md`:

1. Get an implementation plan from the Planner.
1. Parse the plan into phases with explicit, non-overlapping file scopes.
1. Delegate to the Coder and Designer, running independent work in parallel and dependent work sequentially.
1. Send the finished work to the Reviewer for an independent check.
1. Route any requested changes back to the Coder or Designer, then re-review.
1. Integrate the results, verify they hang together, and report the outcome.

Do not stage, commit, or push. Leave all git operations to the user.
