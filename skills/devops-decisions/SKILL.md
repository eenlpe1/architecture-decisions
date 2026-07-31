---
name: devops-decisions
description: Design, audit, or optimize a CI/CD pipeline using the CALMS framework and DORA metrics, and record the decision. Use when the user wants to build a CI/CD pipeline from scratch, audit an existing pipeline for risk and technical debt, optimize pipeline reliability/security/velocity, or wants a DevOps/platform decision written down.
---

# DevOps Decisions

Every CI/CD pipeline choice trades the five CALMS principles against each other — more automation costs setup time, tighter gates slow lead time, broader sharing costs documentation effort. This skill makes that trade-off explicit across three engagements — building a pipeline from scratch, auditing one that exists, or optimizing one that's running — and leaves behind a record of what was decided and why.

## Steps

1. **Frame the engagement** — name the mode (build / audit / optimize), the application or service in scope, its deployment target(s), and the hard constraints (compliance, existing tooling, org maturity, deadline). Done when someone who wasn't in the conversation could tell which mode this is and what's being decided.

2. **Do the mode's legwork** — before recommending anything, gather what the mode needs:
   - **Build** — the application's architecture, tech stack, deployment targets, security/compliance requirements, and the org's existing workflows.
   - **Audit** — walk every dimension in [`AUDIT-DIMENSIONS.md`](AUDIT-DIMENSIONS.md); mark each pass / risk / gap rather than skipping it because it "looks fine."
   - **Optimize** — the pipeline's current DORA metrics baseline (deployment frequency, lead time for changes, change failure rate, MTTR) and the specific complaint driving the request.

   Done when every item for the active mode carries an explicit finding.

3. **Score against CALMS** — for each of the five principles, give a verdict: up, down, or neutral, with a one-line reason. Don't skip a principle because it "obviously doesn't apply" — write "neutral: `<reason>`" rather than omitting it. If a verdict isn't obvious from the one-liner, check that principle's practices in [`CALMS.md`](CALMS.md). Done when all five principles have a stated verdict.

   - **Culture** — shared ownership of the pipeline and blameless response to failure, versus a single gatekeeper team.
   - **Automation** — pipeline, infrastructure, and policy as code; how much still needs a human hand.
   - **Lean** — change size and frequency; how much waste sits between a commit and production.
   - **Measurement** — visibility into the DORA metrics baseline and pipeline health.
   - **Sharing** — how legible the pipeline's standards and decisions are to the next engineer.

4. **Prioritize the recommendation** — order findings or recommendations by business value against engineering effort, and name which CALMS principle each one serves. State the trade-off explicitly: what this plan prioritizes and what it knowingly defers. A recommendation list with nothing deferred hasn't been prioritized — look harder.

5. **Record it** — write the decision as a short markdown file: the mode and scope, the mode's findings, the five-principle CALMS scoring, the prioritized recommendations with rationale, and the deferred trade-off. Reuse an existing decisions location in the repo if one exists (e.g. `docs/adr/`, `docs/decisions/`, `docs/architecture-decisions/`, `docs/pipeline-decisions/`); otherwise create `docs/pipeline-decisions/` and name the file `YYYY-MM-DD-<slug>.md`. Done when the file states chosen actions, not just a comparison.
