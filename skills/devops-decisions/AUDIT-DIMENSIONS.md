# Audit Dimensions

Walk every dimension during an audit engagement; mark each pass / risk / gap.

- **Source control strategy** — repo structure, monorepo vs polyrepo, code ownership
- **Branching model** — trunk-based vs GitFlow vs other, and how it maps to release cadence
- **Build reliability** — flakiness, build time, reproducibility
- **Automated testing** — unit/integration/e2e coverage, and whether tests actually gate merges
- **Artifact management** — versioning, immutability, provenance, registry hygiene
- **Infrastructure as code** — what's codified vs click-ops, state management, drift detection
- **Deployment strategy** — blue/green, canary, rolling, feature flags
- **Rollback mechanisms** — how fast, how automated, and whether it's ever been tested
- **Secrets management** — where secrets live, rotation policy, least-privilege access
- **Security scanning** — SAST/DAST/dependency scanning, and where in the pipeline each runs
- **Observability** — logs/metrics/traces for the pipeline itself and the deploys it produces
- **Governance** — approval requirements, compliance evidence, audit trail
- **Operational resilience** — disaster recovery plan, and whether it's been exercised
