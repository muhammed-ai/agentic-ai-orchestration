# Copilot instructions

Repository-wide custom instructions for GitHub Copilot (chat, CLI, and the coding agent). These apply to every request in this repository.

## About this repository

This repo defines a reusable multi-agent team for orchestrating software work through the GitHub Copilot CLI. The team is five specialist agents that coordinate to plan, design, implement, and verify changes.

- **Orchestrator** - coordinates the work and delegates to specialists.
- **Planner** - researches and produces implementation plans.
- **Coder** - writes code and prepares runnable app support.
- **Designer** - handles UI/UX, accessibility, and visual design.
- **Reviewer** - independently checks finished work for correctness, security, accessibility, and edge cases.

Agent definitions live in `.github/agents/`. Documentation lives in `docs/`.

## How to work here

- Follow the existing repository patterns and file layout.
- Keep agent definitions consistent with each other in structure and tone.
- Every agent definition is a Markdown file with YAML front matter containing `name`, `description`, `model`, and `tools`.
- The `model:` field ships with a `TODO-set-your-model` placeholder. Do not invent a model value; leave the placeholder unless the user asks to set a specific model.
- Prefer clear, explicit prose over clever phrasing in agent and doc files.
- Use ordered lists with `1.` markers where the source files already do.

## Editing rules

- Keep changes scoped to what was requested.
- When you add or rename an agent, update `README.md` and `docs/agent-team.md` so the team roster stays accurate.
- Use relative links between docs and agent files.
- Do not add course-specific or exercise-specific machinery; this repo is a generalized reuse of a GitHub Skills exercise.

## Git control

- Do not stage, commit, or push changes unless the user explicitly asks. The user controls all git operations.
