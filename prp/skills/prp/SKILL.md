---
name: prp
description: Create or execute Product Requirement Prompts (PRPs) for a feature, story, task, specification, TypeScript change, API contract, or React proof of concept. Use when a user asks for a context-rich implementation plan, a PRP, or to implement an existing PRP.
---

# Product Requirement Prompts

Choose the workflow that matches the user's request, then read the corresponding
source workflow from `../../commands/` before acting:

| User intent | Source workflow |
| --- | --- |
| broad feature plan or execution | `prp-base-create.md` or `prp-base-execute.md` |
| user story plan or execution | `prp-story-create.md` or `prp-story-execute.md` |
| small task plan or execution | `prp-task-create.md` or `prp-task-execute.md` |
| TypeScript plan or execution | `prp-ts-create.md` or `prp-ts-execute.md` |
| technical specification plan or execution | `prp-spec-create.md` or `prp-spec-execute.md` |
| product planning | `prp-planning-create.md` |
| React proof of concept | `prp-poc-create-parallel.md` or `prp-poc-execute-parallel.md` |
| API contract | `api-contract-define.md` |
| initialize a task list | `task-list-init.md` |

Treat the selected source workflow as the detailed procedure, with these Codex
adaptations:

- The user's request supplies every occurrence of `$ARGUMENTS`; ask one concise
  question only when the required input is absent.
- Read project instructions in this order when present: `AGENTS.md`, then other
  repository guidance and configuration files. Do not require `CLAUDE.md`.
- Replace a named Claude subagent with the same analysis role in the current task.
  Delegate only when the environment makes that useful; otherwise perform the
  analysis yourself and preserve its findings in the PRP.
- References beginning with `@PRPs/` refer to files under `../../PRPs/`.
  Read the indicated template before creating a PRP.
- For a create workflow, inspect the target repository before writing the plan.
  Include exact paths, existing patterns, dependencies, tests, ordered atomic
  tasks, and commands that can actually validate the change.
- For an execute workflow, first read the PRP file, implement only its approved
  scope, run relevant validation, and report results and remaining risks.
- Never invent test, build, or deployment commands. Discover them from the target
  repository. Ask before irreversible external actions.

The included analyst guidance is in `../../agents/`; use it to deepen codebase
and library research when relevant. PRP templates, examples, and reference
material remain in `../../PRPs/`.
