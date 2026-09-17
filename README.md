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
.github/agents/                  Agent definitions (orchestrator, planner, coder, designer, reviewer)
.github/copilot-instructions.md  Repo-wide Copilot custom instructions
.github/instructions/            Path-scoped instructions (e.g. agent-file conventions)
.github/prompts/                 Reusable prompt files for common workflows
.github/workflows/               CI checks and the Copilot coding agent setup steps
.github/ISSUE_TEMPLATE/          Issue forms
.github/PULL_REQUEST_TEMPLATE.md Pull request template
.github/CODEOWNERS               Review ownership
.github/dependabot.yml           Dependency update schedule
docs/agent-team.md               How the team is organized and coordinated
CONTRIBUTING.md                  Contribution guidelines
```

## Configuration

- **`.github/copilot-instructions.md`** applies to every Copilot request in this repo. GitHub Copilot picks it up automatically.
- **`.github/instructions/*.instructions.md`** apply only to files matching each file's `applyTo` glob.
- **`.github/prompts/*.prompt.md`** are reusable prompts you can invoke for common workflows (orchestrating a task, scaffolding a new agent).
- **`.github/workflows/copilot-setup-steps.yml`** prepares the environment for the Copilot coding agent. Extend it as the repo grows.
- Placeholders such as `TODO-set-your-github-owner` (in `CODEOWNERS`) and `TODO-set-your-copyright-holder` (in `LICENSE`) should be filled in for your project.

## Origin

The agent definitions were adapted from a GitHub Skills exercise on agent orchestration, generalized here for reuse across projects (course-specific demo files and exercise machinery removed).
