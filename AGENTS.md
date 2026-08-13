# Repository guidance

This repository publishes the same architecture-decision skills for Codex and Claude Code.

- Keep the canonical skill content under `skills/`; do not duplicate it per client.
- Codex metadata lives in `.codex-plugin/plugin.json` and the root `marketplace.json`.
- Claude Code metadata lives in `.claude-plugin/`.
- When behavior changes, update the relevant `SKILL.md` and its directly referenced supporting files.
- When publishing a release, keep the versions in `.codex-plugin/plugin.json` and `.claude-plugin/plugin.json` aligned.
- Validate the root with the Codex plugin validator after changing `.codex-plugin/plugin.json`.
- Validate each changed skill with the Codex skill validator before publishing.
- Keep README installation, update, and repository-layout instructions accurate for both clients.
