# architecture-decisions

Personal Claude Code skills for making and recording infrastructure decisions.

## Skills

- **infra-decisions** — evaluate an AWS infrastructure choice against the AWS Well-Architected Framework's six pillars and record the decision.
- **devops-decisions** — design, audit, or optimize a CI/CD pipeline using the CALMS framework and DORA metrics, and record the decision.

Both end the same way: every pillar/principle gets an explicit verdict, the trade-off you're accepting gets named out loud, and the decision is written to a markdown file in the repo you're working in.

## Install

```
/plugin marketplace add eenlpe1/architecture-decisions
/plugin install architecture-decisions@eenlpe1
```

## Update

Pull the latest and reinstall, or bump the version in `.claude-plugin/plugin.json` and re-run `/plugin install`.
