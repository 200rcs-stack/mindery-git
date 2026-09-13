# MINDERY Engine Agent Rules

These rules apply to every coding or operational agent working in this repository.

## Mission
Build MINDERY Engine as a reliable, auditable multi-agent system that can plan, create, review, distribute, measure, and improve marketing work for MINDERY books, content, and commerce products.

## Working contract
1. Read `docs/MINDERY_ENGINE_1.0.md` before material changes.
2. Never optimize for activity. Optimize for verified outcomes.
3. State assumptions explicitly when evidence is missing.
4. Prefer small, reviewable changes over giant rewrites.
5. Every feature needs acceptance criteria and a test or verifiable check.
6. Never expose secrets, tokens, credentials, cookies, or private user data in commits, logs, prompts, screenshots, fixtures, or examples.
7. External publishing, money movement, deletion, account settings, paid campaign changes, and irreversible actions require an explicit approval boundary unless the specific workflow has been granted trusted-autonomy status.
8. Prefer official APIs/connectors for external platform actions. Browser automation is a fallback, not the default.
9. Do not create infinite retries. Respect retry limits and escalate persistent failures.
10. Record meaningful decisions and tradeoffs.

## Cross-review
- If Codex implements, Anti-Gravity or another independent reviewer should validate the end-to-end behavior.
- If Anti-Gravity implements, Codex should review architecture, code quality, tests, security, and failure handling.
- A final release may not rely solely on the implementing agent's self-review.

## Cost discipline
Before expensive model/tool calls, determine whether deterministic code, cached data, existing repository logic, or a cheaper execution path can solve the task.

Each orchestrated task should support:
- `max_calls`
- `max_tokens`
- `max_cost`
- `timeout_ms`
- `retry_limit`
- `approval_level`

## Architecture preferences
- TypeScript-first for the current web/orchestration stack unless there is a strong reason otherwise.
- Structured JSON contracts between agents.
- Idempotent jobs where possible.
- Durable audit logs for agent/tool actions.
- Queue-based background work for long tasks.
- Explicit state machines for workflows that can publish, spend, delete, or mutate external systems.
- Provider/model adapters so the system is not locked to one model vendor.

## Definition of done
A task is not done merely because code was generated. It is done when:
- acceptance criteria are met,
- relevant tests/checks pass,
- failure modes are handled,
- cost/latency impact is understood,
- logs/evidence exist,
- independent review is complete when required,
- documentation is updated when behavior or architecture changed.
