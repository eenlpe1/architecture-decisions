---
name: infra-decisions
description: Evaluate an AWS infrastructure choice against the AWS Well-Architected Framework and record the decision. Use when the user is choosing between AWS services or architectures, auditing an existing AWS setup against the Well-Architected pillars, or wants an infrastructure decision written down.
---

# Infra Decisions

Every AWS infrastructure choice trades pillars against each other — more redundancy costs more, tighter security slows delivery, a smaller footprint can cost performance. This skill makes that trade-off explicit instead of leaving it implicit, and leaves behind a record of what was decided and why.

## Steps

1. **Frame the decision** — state the question being decided, the options on the table (name at least two; a bare "should we do X" is one option in disguise, so surface the alternative), and the hard constraints (budget, compliance, existing architecture, deadline). Done when someone who wasn't in the conversation could tell what's being chosen between.

2. **Score every pillar** — for each of the six pillars below, give a verdict: up, down, or neutral, with a one-line reason. Don't skip a pillar because it "obviously doesn't apply" — write "neutral: `<reason>`" rather than omitting it. If a verdict isn't obvious from the one-liner, check that pillar's design principles in [`PILLARS.md`](PILLARS.md). Done when all six pillars have a stated verdict.

   - **Operational Excellence** — running and monitoring systems, and continually improving process: automating changes, responding to events, defining standards for daily operations.
   - **Security** — protecting data and systems: confidentiality and integrity of data, managing permissions, detecting security events.
   - **Reliability** — a workload performing its function and recovering quickly from failure: distributed system design, recovery planning, adapting to changing demand.
   - **Performance Efficiency** — structured, streamlined use of compute resources: picking resource types and sizes for the workload, monitoring performance, staying efficient as demand and technology evolve.
   - **Cost Optimization** — avoiding unnecessary spend: understanding spend over time, controlling fund allocation, right-sizing and right-quantity resources, scaling to match business need.
   - **Sustainability** — minimizing the environmental impact of running workloads: the shared responsibility model for sustainability, understanding impact, maximizing utilization per unit of work.

3. **Name the sacrifice** — pillars will conflict (Cost Optimization down, Reliability up, say). State which pillar(s) this decision prioritizes and which it knowingly sacrifices, and why that ordering is right for this workload right now. Done when one sentence names the accepted downside and its pillar. A decision with no sacrificed pillar hasn't been stress-tested — look harder.

4. **Record it** — write the decision as a short markdown file: the question, the options considered, the six-pillar scoring, the chosen option, and the sacrifice. Reuse an existing decisions location in the repo if one exists (e.g. `docs/infrastructure/`, `docs/adr/`, `docs/decisions/`); otherwise create `docs/architecture-decisions/` and name the file `YYYY-MM-DD-<slug>.md`. Done when the file states a chosen option, not just a comparison.
