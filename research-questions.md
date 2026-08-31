# Research Questions

This is the current prioritized research backlog. The order can change as evidence from earlier questions changes what is worth investigating next.

## 1. Division of labor between human, thinking assistant, and coding agent — ACTIVE

**Core question**

How are effective solo builders using ChatGPT/Claude-style thinking agents together with Codex/Claude Code-style coding agents and GitHub to build real products — and where do they draw the boundaries between product thinking, planning, implementation, review, and release?

Things to investigate:

- How much product thinking and grooming happens outside the coding agent?
- When does a general-purpose AI assistant add leverage versus unnecessary handoff overhead?
- How detailed are implementation prompts when durable context already exists in GitHub and the repository?
- Do effective builders let coding agents participate directly in architecture and implementation planning?
- What role does GitHub play as durable shared memory between humans and multiple agents?
- When is an orchestration layer useful?
- Which responsibilities should remain explicitly human?

## 2. Optimal task size and agent economics

What task size produces the best quality, reliability, context efficiency, and usage cost? Compare tiny issues, coherent medium-sized tasks, batches, and larger end-to-end features.

### Field observation — visual tuning can be disproportionately expensive

During PedalFish header-logo work on 2026-08-31, the coding agent correctly implemented the initial branding change, but subsequent human visual acceptance produced several very small iterations: swapping/refining the logo artwork, changing the rendered size from roughly 42px to 52px and then toward 60px, and adjusting crop/visual weight.

Each tiny visual adjustment risked paying the full coding-agent workflow cost again: repository context/reconciliation, implementation reasoning, broad tests, typecheck, lint, production build, diff checks, commit, push, Preview deployment, and another human inspection. The implementation risk of these later changes was very low while the token/usage cost was comparatively high.

This suggests a useful research hypothesis rather than a settled rule:

> Separate implementation from visual-tuning loops. Use a capable coding agent to establish the feature correctly, then use the cheapest reliable path for small CSS/layout/image-size iterations, with focused validation during tuning and full validation once human visual acceptance is reached.

Questions to test:

- When can visual-only iterations safely use a cheaper/faster model than the initial implementation?
- When is a direct local edit more economical than another coding-agent task?
- Which focused tests are sufficient during repeated low-risk visual tuning?
- Can full-suite/typecheck/lint/build validation be deferred until the human accepts the visual result without materially increasing risk?
- How should the workflow distinguish a genuinely low-risk presentation tweak from a visual change that affects responsive behavior, accessibility, or application structure?
- Does batching several human visual corrections into one agent pass materially reduce usage without slowing feedback too much?

This is concrete evidence for the broader task-size/economics question: a workflow optimized for reliable feature implementation may be unnecessarily expensive when applied unchanged to iterative visual polishing.

## 3. Parallel coding agents

How are practitioners successfully running multiple coding agents at once? Investigate worktrees, branch ownership, dependency management, merge strategy, reviewer agents, and the actual throughput gain versus coordination cost.

## 4. Context loading and repository knowledge

How much context should an agent load, how should it be structured, and when does documentation become counterproductive? Compare agent instruction files, layered docs, issues, generated context manifests, ADRs, and other approaches.

## 5. Checkpoint, interruption, and handoff

What is the most reliable and economical way to resume work after quota exhaustion, interruption, or transfer to another agent? Compare Git commits, issue comments, handoff files, session summaries, and agent-generated checkpoints.

## 6. Human acceptance versus automated testing

What should humans actually test when coding agents can run increasingly sophisticated automated and browser-based tests? Where should unit, integration, E2E, Preview, smoke, and human acceptance sit in an agentic workflow?

## 7. Git branching and deployment for agentic development

What branching/deployment models work best with multiple AI agents and Preview environments? Compare branch-per-agent, worktrees, stacked branches, trunk-based development, feature flags, and ephemeral environments.

## 8. Right-sized safety for a solo AI-assisted builder

How much release, migration, review, and operational safety is economically justified for a solo builder shipping real software? Where is the boundary between useful professional discipline and process whose cost exceeds the risk it mitigates?

## 9. Market maturity and professional positioning

Where do the problems and practices explored in this repository sit relative to the broader software-engineering and AI-development market?

The purpose is not to establish whether the work is "cutting edge" for its own sake. The practical question is how to describe this experience accurately to employers, collaborators, and other practitioners without presenting established practice as novel or underselling experience that is still uncommon in normal engineering organizations.

Things to investigate:

- Which agentic-development practices are already mainstream, emerging, specialist, or genuinely experimental?
- How widely are engineering teams actually using repo-grounded coding agents, durable agent instructions, human/agent handoffs, parallel agents, and agentic release workflows in production work?
- Which problems have mature industry solutions versus active practitioner experimentation?
- How quickly is adoption moving from individual developers into engineering organizations?
- What vocabulary are employers and engineering leaders using for this work?
- Which aspects of hands-on agentic product development are meaningful professional differentiators today?
- How should practical experience be discussed in interviews without claiming novelty that is not supported by the market?

This question should be revisited as the market changes; its answer is inherently time-sensitive.

## Research principle

Do not turn an open question into another workflow rule merely because a plausible answer can be invented. Research existing practice first, test promising approaches against real product work, and only then promote useful findings into durable ways of working.
