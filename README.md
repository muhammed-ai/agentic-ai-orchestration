# Agentic AI Orchestration

A reusable multi-agent team for orchestrating software work through the GitHub Copilot CLI. The team is made of four specialist agents that coordinate to plan, design, implement, and verify changes.

## The team

- **Orchestrator** - coordinates the work and delegates to specialists.
- **Planner** - researches and produces implementation plans.
- **Coder** - writes code and prepares runnable app support.
- **Designer** - handles UI/UX, accessibility, and visual design.
- **Reviewer** - independently checks the finished work for correctness, security, accessibility, and edge cases.

Agent definitions live in [`.github/agents/`](.github/agents/). See [`docs/agent-team.md`](docs/agent-team.md) for details on how they work together.

## Getting started

1. Open the `model:` field in each file under `.github/agents/` and set it to a model you have access to (they ship with a `TODO-set-your-model` placeholder).
1. Start the Orchestrator from the GitHub Copilot CLI and give it a task.
1. The Orchestrator will pull in the Planner, Coder, and Designer as needed.

## Structure

```
.github/agents/    Agent definitions (orchestrator, planner, coder, designer)
docs/agent-team.md How the team is organized and coordinated
```

## Origin

The agent definitions were adapted from a GitHub Skills exercise on agent orchestration, generalized here for reuse across projects (course-specific demo files and exercise machinery removed).
