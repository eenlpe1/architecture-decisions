# architecture-decisions

Personal Claude Code skills for making and recording infrastructure decisions — AWS choices scored against the Well-Architected Framework, CI/CD choices scored against CALMS + DORA.

## Table of Contents

- [Skills](#skills)
  - [infra-decisions](#infra-decisions)
  - [devops-decisions](#devops-decisions)
- [Installation](#installation)
- [Usage](#usage)
- [Updating](#updating)
- [Repository Structure](#repository-structure)
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

Requires [Claude Code](https://code.claude.com) with plugin support.

```
/plugin marketplace add eenlpe1/architecture-decisions
/plugin install architecture-decisions@eenlpe1
/reload-plugins
```

## Usage

Both skills are model-invoked — Claude reaches for them automatically when a conversation matches their triggers (see the [Skills](#skills) table), no explicit call needed. You can also name one directly:

```
architecture-decisions:infra-decisions
architecture-decisions:devops-decisions
```

## Updating

To pull whatever's newest on `main`:

```
/plugin marketplace update eenlpe1
/plugin install architecture-decisions@eenlpe1
/reload-plugins
```

## Repository Structure

```
architecture-decisions/
├── .claude-plugin/
│   ├── marketplace.json   # marketplace metadata (name: eenlpe1)
│   └── plugin.json        # plugin metadata + skill list (name: architecture-decisions)
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

## Publishing a Change

1. Edit the relevant skill file(s) under `skills/`.
2. Bump `version` in [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json).
3. Commit and push to `main`.
4. Anywhere it's installed, run `/plugin marketplace update eenlpe1` then `/plugin install architecture-decisions@eenlpe1` to pull the new version.
