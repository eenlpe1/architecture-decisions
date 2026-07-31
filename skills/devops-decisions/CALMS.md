# CALMS Practices

Consult a principle's practices when its verdict in step 3 isn't obvious from the one-liner alone.

## Culture
- Blameless postmortems — treat failure as a learning signal, not a target for blame
- Shared ownership of the pipeline across dev, ops, and security, not a single gatekeeper team
- Cross-functional review on pipeline changes, not a single approver

## Automation
- Everything as code: pipelines, infrastructure, policy
- GitOps — the repo is the source of truth for both application and environment state
- Automated quality gates block a merge or deploy rather than relying on manual review
- Immutable deployments — rebuild and redeploy rather than patch in place

## Lean
- Small, frequent, reversible changes over big-bang releases
- Eliminate manual hand-offs and approval queues that don't add safety
- Shift testing and security left — catch defects at the earliest cheap stage

## Measurement
- Track the DORA metrics trend over time, not just their current value
- Comprehensive monitoring and alerting on the pipeline itself, not just the application it deploys
- Make pipeline health visible to the whole team, not only to whoever built it

## Sharing
- Policy as code, so standards are legible and enforced the same way everywhere
- Document decisions where the next engineer will find them (runbooks, ADRs)
- Continuous feedback loops from production incidents back into pipeline design
