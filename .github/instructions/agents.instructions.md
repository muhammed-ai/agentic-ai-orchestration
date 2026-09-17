---
applyTo: ".github/agents/**/*.agent.md"
---

# Agent definition instructions

Path-scoped instructions that apply when working on agent definition files under `.github/agents/`.

## Front matter

Every `*.agent.md` file must begin with YAML front matter containing these keys, in this order:

- `name` - the agent's display name (e.g. `Coder`).
- `description` - one sentence describing what the agent does.
- `model` - the model the agent runs on. Ships as `TODO-set-your-model`; leave the placeholder unless told otherwise.
- `tools` - a list of tool identifiers the agent is allowed to use.

## Body

- Open with a short second-person statement of the agent's role ("You are ...", "You write ...").
- Use section headings (`##`) to group principles, rules, and execution model.
- Use ordered lists with `1.` markers for sequential steps and rules.
- Keep the tone direct and free of filler.

## Tool scoping

- Grant only the tools an agent needs. For example, the Reviewer must not have `edit`, so review stays an independent gate.
- Keep tool lists consistent with the agent's stated responsibilities.

## Consistency

- When adding, renaming, or removing an agent, update `README.md` and `docs/agent-team.md`.
- Every agent must include a "Git control" section stating it will not stage, commit, or push unless the user explicitly asks.
