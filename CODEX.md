# Codex support

This repository supports both Claude Code and Codex.

- Claude Code continues to use `.claude-plugin/`, `commands/`, and `agents/`.
- Codex uses each plugin's `.codex-plugin/plugin.json` and `skills/` directory.

The Codex skills deliberately reuse the same PRP templates, source workflows,
agent role guidance, and content-generation rubric. This keeps both hosts on one
source of truth instead of maintaining diverging copies of every workflow.

## Install locally in Codex

From the repository root, add it as a local marketplace and install the plugin:

```sh
codex plugin marketplace add .
codex plugin add prp@rapid-shipping
codex plugin add content-gen@rapid-shipping
```

Start a new Codex thread after installation so that the new skills are available.

## Use

Use natural language, for example:

- "Create a story PRP for adding OAuth login."
- "Execute `PRPs/working-memory/oauth/story_oauth-login.md`."
- "Run the content-generation workflow for these product stories."

The PRP and content-generation source directories are intentionally shared by
both hosts. Do not move or rename them without updating both host integrations.
