# Contributing

Thanks for helping improve Architecture Decisions. Contributions may update the shared skills, their supporting references, or the Codex and Claude Code plugin metadata.

## Before making a change

- Open an issue first for substantial behavior changes or new skills.
- Keep each pull request focused on one concern.
- Do not duplicate skill content for individual clients. Codex and Claude Code share the canonical files under `skills/`.
- Preserve the existing decision workflow: frame the choice, evaluate every applicable dimension, state the accepted trade-off, and record a concrete decision.

## Changing a skill

Each skill lives in `skills/<skill-name>/SKILL.md`. Supporting material that the skill directly references belongs in the same directory.

When changing a skill:

1. Keep its frontmatter `name` aligned with its directory name.
2. Make its `description` specific enough to identify when the skill should activate.
3. Use relative links for supporting files.
4. Include explicit completion criteria for workflow steps.
5. Update the README if triggers, behavior, outputs, installation, or repository structure change.

## Plugin metadata

The same skills are distributed through two plugin manifests:

- `.codex-plugin/plugin.json` for Codex
- `.claude-plugin/plugin.json` for Claude Code

Keep their plugin names and semantic versions aligned. When preparing a release, bump both versions in the same pull request.

## Validation

Before opening a pull request:

1. Validate `.codex-plugin/plugin.json` with the Codex plugin validator.
2. Validate every changed `skills/<skill-name>` directory with the Codex skill validator.
3. Confirm that all JSON files parse successfully.
4. Run `git diff --check` to detect whitespace errors.
5. Review the rendered Markdown and verify all relative links.

If the Codex validation tools are unavailable locally, mention that in the pull request and include the checks you were able to run.

## Pull requests

Describe:

- the problem being solved;
- the behavior or documentation changed;
- an example prompt when skill behavior changes;
- validation performed; and
- any accepted limitation or follow-up work.

By contributing, you agree that your contribution is licensed under the [MIT License](LICENSE).
