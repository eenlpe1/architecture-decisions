# Architecture Decisions

Codex and Claude Code skills for making and recording infrastructure decisions — AWS choices scored against the Well-Architected Framework, CI/CD choices scored against CALMS + DORA.

Current plugin version: **1.0.1** for both Codex and Claude Code.

## Table of Contents

- [Skills](#skills)
  - [infra-decisions](#infra-decisions)
  - [devops-decisions](#devops-decisions)
- [Installation](#installation)
- [Usage](#usage)
- [Updating](#updating)
- [Repository Structure](#repository-structure)
- [Contributing](#contributing)
- [License](#license)
- [Publishing a Change](#publishing-a-change)

## Skills

| Skill | Use when | Scores against | Ends in |
|---|---|---|---|
| [`infra-decisions`](skills/infra-decisions/SKILL.md) | Choosing between AWS services/architectures, or auditing an existing AWS setup | The 6 Well-Architected pillars | A recorded decision file |
| [`devops-decisions`](skills/devops-decisions/SKILL.md) | Building, auditing, or optimizing a CI/CD pipeline | The 5 CALMS principles + DORA metrics | A recorded decision file |

Both skills follow the same shape: frame the decision → score every pillar/principle explicitly, none skipped → name the trade-off being accepted → write it down as markdown in the repo you're working in.

### infra-decisions

Evaluates an AWS infrastructure choice against the AWS Well-Architected Framework's six pillars — Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability — and records the decision.

- [`skills/infra-decisions/SKILL.md`](skills/infra-decisions/SKILL.md) — the full process
- [`skills/infra-decisions/PILLARS.md`](skills/infra-decisions/PILLARS.md) — each pillar's design principles, consulted when a verdict isn't obvious

### devops-decisions

Designs, audits, or optimizes a CI/CD pipeline using the CALMS framework — Culture, Automation, Lean, Measurement, Sharing — and DORA metrics, and records the decision.

- [`skills/devops-decisions/SKILL.md`](skills/devops-decisions/SKILL.md) — the full process
- [`skills/devops-decisions/CALMS.md`](skills/devops-decisions/CALMS.md) — practices behind each CALMS principle
- [`skills/devops-decisions/AUDIT-DIMENSIONS.md`](skills/devops-decisions/AUDIT-DIMENSIONS.md) — the checklist used in audit mode

## Installation

### Codex

Requires Codex with plugin support. Add this GitHub repository as a marketplace, then install the plugin:

```sh
codex plugin marketplace add eenlpe1/architecture-decisions
codex plugin add architecture-decisions@eenlpe1
```

Start a new Codex thread after installation so the skills are loaded.

### Claude Code

Requires [Claude Code](https://code.claude.com) with plugin support.

```text
/plugin marketplace add eenlpe1/architecture-decisions
/plugin install architecture-decisions@eenlpe1
/reload-plugins
```

## Usage

Both skills are model-invoked — Codex or Claude reaches for them automatically when a conversation matches their triggers (see the [Skills](#skills) table). You can also name one directly; installed skills are namespaced by the plugin:

```
architecture-decisions:infra-decisions
architecture-decisions:devops-decisions
```

## Updating

For Codex, refresh the marketplace and reinstall the plugin, then start a new thread:

```sh
codex plugin marketplace upgrade eenlpe1
codex plugin add architecture-decisions@eenlpe1
```

For Claude Code:

```text
/plugin marketplace update eenlpe1
/plugin install architecture-decisions@eenlpe1
/reload-plugins
```

## Repository Structure

```
architecture-decisions/
├── .codex-plugin/
│   └── plugin.json        # Codex plugin metadata
├── .claude-plugin/
│   ├── marketplace.json   # marketplace metadata (name: eenlpe1)
│   └── plugin.json        # plugin metadata + skill list (name: architecture-decisions)
├── marketplace.json       # Codex marketplace catalog
├── AGENTS.md              # repository guidance for Codex
├── CONTRIBUTING.md        # contribution workflow
├── LICENSE                # MIT license
├── skills/
│   ├── infra-decisions/
│   │   ├── SKILL.md
│   │   └── PILLARS.md
│   └── devops-decisions/
│       ├── SKILL.md
│       ├── CALMS.md
│       └── AUDIT-DIMENSIONS.md
└── README.md
```

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the development, validation, and pull-request workflow.

## License

This project is licensed under the [MIT License](LICENSE).

## Publishing a Change

1. Edit the relevant skill file(s) under `skills/`.
2. Bump `version` in both [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) and [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json).
3. Commit and push to `main`.
4. Refresh and reinstall the plugin using the relevant client's commands under [Updating](#updating).
