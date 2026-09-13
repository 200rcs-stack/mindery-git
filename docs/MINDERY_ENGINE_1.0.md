# MINDERY Engine 1.0

## Mission
MINDERY Engine is a multi-agent operating system for turning an idea, book, product, or customer problem into validated strategy, content, creative assets, distribution, sales learning, and the next iteration.

The goal is not full autonomy at any cost. The goal is reliable autonomy with evidence, audit trails, cost control, and explicit approval gates.

## Core operating principle
One agent proposes. Another agent challenges. Tools verify. Tests decide. High-impact external actions require an approval gate until reliability is proven.

## Agent topology

### 1. CEO Orchestrator
- Breaks goals into tasks.
- Chooses which specialist agents run.
- Sets acceptance criteria, budget, deadlines, and approval level.
- Does not perform expensive specialist work unless necessary.

### 2. Market & Customer Intelligence Agent
- Customer pains, search intent, competitor positioning, trend signals.
- Produces evidence-backed opportunity briefs.

### 3. Offer / Product Agent
- Product, book, service, pricing, bundle, positioning and offer design.
- For commerce, consumes outputs from the sourcing-agent rather than duplicating its crawlers.

### 4. Content Strategy Agent
- Creates content pillars, hooks, scripts, series, CTAs and channel adaptations.
- Every content item must map to a customer problem and funnel stage.

### 5. Creative & Video Agent
- Produces shot plans, image/video generation prompts, edits, captions, thumbnails and reusable creative packages.
- Stores asset lineage and source references.

### 6. Distribution Agent
- Prepares or publishes content through official platform APIs/connectors when available.
- Uses dry-run mode by default.
- Does not publish, delete, spend money, or change campaign budgets without the configured approval policy.

### 7. Growth Analytics Agent
- Measures reach, retention, click-through, conversion, CAC/ROAS where available.
- Explains why results moved and creates next experiments.

### 8. Codex Engineering Agent
- Owns code implementation, refactors, tests, migrations, CI failures and code review.
- Works through Git branches and pull requests.
- Must not silently bypass failing tests.

### 9. Anti-Gravity Execution Agent
- Owns browser/tool automation, data collection, operational workflows and cheaper routine execution.
- Reuses existing sourcing-agent capabilities where applicable.
- Produces structured evidence and logs for reviewers.

### 10. Red-Team / QA Agent
- Attempts to disprove the plan or output.
- Checks factual grounding, duplication, platform policy risks, broken links, bad assumptions, prompt injection exposure, secret leakage and unsafe external actions.
- Can block release.

## Codex <-> Anti-Gravity cross-review protocol
1. CEO creates a task with acceptance criteria and budget.
2. Primary agent produces a proposal or implementation on a task branch.
3. Primary agent runs its own tests/checks and attaches evidence.
4. The other system reviews independently.
   - Anti-Gravity implementation -> Codex technical/code review.
   - Codex implementation -> Anti-Gravity end-to-end workflow and user-path review.
5. QA agent runs release checks.
6. Only PASS / PASS_WITH_NOTES can move forward.
7. External publishing, spending, deletion and account-level changes remain approval-gated until a specific workflow earns trusted-autonomy status.

## Single source of truth
GitHub is the project ledger.

Every material task should be represented by one or more of:
- Issue: goal, acceptance criteria, budget, owner, status.
- Branch: implementation.
- Pull request: proposed change and review conversation.
- Test/eval output: evidence.
- Decision log: why the change was accepted.

No agent may claim completion without a verifiable artifact.

## Cost governor
The system should route work by value, not prestige.

- Cheap/routine: deterministic code, cached retrieval, local scripts, low-cost model, Anti-Gravity.
- Medium: content variants, classification, summaries, monitoring.
- Expensive/high-reasoning: architecture, ambiguous debugging, final code review, difficult synthesis, high-impact decisions.
- Each task receives max_calls, max_tokens, max_cost, timeout, retry_limit and escalation rules.
- Repeat failures escalate rather than loop indefinitely.
- Cache stable research and reuse structured outputs.

## Autonomy levels
L0 Recommend only.
L1 Draft and wait for approval.
L2 Execute reversible internal actions and show result.
L3 Execute pre-approved external actions within hard limits.
L4 Fully autonomous workflow only after measured reliability and rollback tests.

Initial default: L1 for publishing and paid actions, L2 for repository/internal analysis.

## Publishing safety
Before any post is published, verify:
- correct brand and account
- correct destination/channel
- copy and media match
- links resolve
- no accidental private data
- no prohibited claims or copyright-risk assets
- schedule/timezone
- duplicate-post check
- rollback/delete path is known

## Learning loop
Every campaign or content item must write back:
- hypothesis
- creative/content version
- audience/channel
- publish time
- reach/impressions
- watch/retention where available
- clicks
- conversions/revenue where available
- cost
- qualitative comments
- lesson
- next experiment

The engine must learn from results, not only generate more content.

## Phase plan

### Phase 0 - Foundation
- Establish GitHub task/review protocol.
- Add agent registry, task schema, audit log and cost governor.
- Reuse sourcing-agent capabilities rather than rewrite them.

### Phase 1 - Strategy to content package
Input: one product/book/idea.
Output: customer brief, positioning, 30 hooks, 10 short-form concepts, 3 full scripts, CTA set, channel plan, measurement plan.
No automatic publishing yet.

### Phase 2 - Creative production
Generate/edit images, video packages, subtitles, thumbnails and descriptions from approved content plans.
Asset QA is mandatory.

### Phase 3 - Approval-based distribution
Connect official platform APIs/connectors.
Agent prepares posts and schedules. Human approves the batch.

### Phase 4 - Closed-loop growth
Ingest channel/store analytics, identify winners/losers, and automatically propose the next experiments.

### Phase 5 - Trusted autonomy
Only workflows with strong measured reliability graduate to automatic publishing or routine execution.

## First vertical slice
The first end-to-end demonstration should use one real MINDERY asset, preferably a book or one existing commerce product.

Success criteria:
- One brief becomes three channel-specific pieces of content.
- Codex and Anti-Gravity independently review the workflow.
- Every step has logs and a cost record.
- Final package can be approved with one action.
- After publishing is connected, performance data can flow back into the next iteration.

## Non-negotiables
- No hidden spend.
- No hidden publishing.
- No secret leakage.
- No claim of success without evidence.
- No infinite retry loops.
- No agent reviewing only its own work for final release.
- Prefer official APIs over brittle browser automation for publishing/account actions.
- Keep humans at the policy boundary, not in every tiny task.
