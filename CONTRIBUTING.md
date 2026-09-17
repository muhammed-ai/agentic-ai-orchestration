# Contributing

Thanks for helping improve the agentic AI orchestration team.

## Ground rules

- Keep changes scoped to what you set out to do.
- Match the existing structure and tone of the files you edit.
- Do not add course-specific or exercise-specific machinery. This repo is a generalized reuse of a GitHub Skills exercise.

## Working on agent definitions

Agent definitions live in `.github/agents/` as `*.agent.md` files. Each one must have YAML front matter with these keys, in order:

- `name`
- `description`
- `model` (ships as `TODO-set-your-model`; leave the placeholder unless you are intentionally setting a model)
- `tools`

Grant each agent only the tools it needs. The Reviewer must not have `edit` access so review stays an independent gate.

When you add, rename, or remove an agent, update `README.md` and `docs/agent-team.md` so the roster and flow stay accurate.

See `.github/instructions/agents.instructions.md` for the full conventions.

## Configuration files

- `.github/copilot-instructions.md` - repo-wide Copilot instructions.
- `.github/instructions/` - path-scoped instructions.
- `.github/prompts/` - reusable prompt files.
- `.github/workflows/` - CI and the Copilot coding agent setup steps.

## Pull requests

1. Create a branch for your change.
1. Make sure CI passes (agent front-matter validation runs on every PR).
1. Fill out the pull request template.
1. Leave git operations to the repo maintainers when working through the agents; the team never commits or pushes on its own.
