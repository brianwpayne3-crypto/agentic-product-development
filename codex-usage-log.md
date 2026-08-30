# Codex usage log

This is a lightweight empirical log of real Codex work. It is maintained outside Codex so the system being measured is not responsible for deciding what usage evidence gets recorded.

The goal is not perfect telemetry. The goal is enough consistent evidence to make better decisions about model, effort, speed, task routing, and eventual parallel-agent economics.

## Measurement procedure

For each meaningful Codex run:

1. Before dispatch, record the intended task, project/issue, Model, Effort, and Speed.
2. When practical, Brian reports the visible 5-hour-window usage and weekly usage before the run.
3. After the run, Brian reports the visible usage again and the observed elapsed time.
4. ChatGPT calculates and records the deltas rather than asking Codex to self-report efficiency.
5. Record whether the task succeeded, required intervention, required escalation to another setting/model, created rework, or failed acceptance.
6. Keep 5-hour-window and weekly usage separate. Never infer one from the other.
7. Approximate observations are useful but must be labeled approximate rather than presented as precise measurements.

Usage percentages are account/UI observations, not equivalent to API token counts or dollar cost. Cross-task comparisons should account for task type and complexity rather than treating every percentage point as interchangeable work.

## Runs

| # | Date | Project | Issue / task | Task type | Model | Effort | Speed | 5-hour usage delta | Weekly usage delta | Elapsed time | Outcome | Intervention / escalation | Rework | Notes |
|---|---|---|---|---|---|---|---|---:|---:|---|---|---|---|---|
| 1 | 2026-08-30 | PedalFish | #106 Production application release and closeout | Production release / verification | 5.6 Sol | Light | Standard | 16% | — | >8 min observed | Success | None reported | None reported | Accepted implementation was already complete. Run reconciled release state, deployed Production, performed smoke verification, recorded evidence, and closed #106. No Production operational data/schema mutation during this release. This is a baseline observation, not evidence that 16% is typical for Sol Light. |

## What we are trying to learn

Over a series of real tasks, use this log to test questions such as:

- How often can Terra replace Sol for well-groomed implementation work?
- Which bounded tasks can Luna complete reliably?
- Does increasing Effort rescue a cheaper model economically, or is escalating Model more efficient?
- How much capacity does Fast consume relative to the elapsed time it saves in real workflows?
- Does stronger issue grooming allow lower-cost coding settings to succeed?
- What is the capacity consumed per accepted/landed change, including failed attempts and rework?
- When we eventually test parallel agents, does the elapsed-time benefit justify combined capacity and integration cost?

Do not promote a model-routing hypothesis into a durable default from one or two runs. Accumulate real-product evidence first.
