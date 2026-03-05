# PR Review Checklist — Agentic Engineering

## Architecture
- [ ] Aligns with intended architecture and boundaries
- [ ] No accidental cross-layer coupling
- [ ] No unnecessary new abstractions

## Correctness
- [ ] Handles expected flows + edge cases
- [ ] Input validation is explicit
- [ ] Clear error responses / behavior

## Security
- [ ] No secrets in code/logs
- [ ] Auth/RBAC checks are enforced server-side where relevant
- [ ] Safe handling of PII/sensitive content

## Performance & Reliability
- [ ] No obvious N+1 patterns
- [ ] Pagination where required
- [ ] Idempotency / retries handled if relevant

## Observability
- [ ] Logs include useful context (request id / correlation id)
- [ ] Errors are trackable
- [ ] Key actions auditable when needed

## Tests & Docs
- [ ] Tests cover critical paths
- [ ] Docs updated (readme/architecture/notes)
- [ ] Migration/rollout notes included if schema/infra changed

## AI-generated code checks (extra)
- [ ] Output is not over-engineered
- [ ] Libraries used correctly and not outdated
- [ ] Any AI-generated sections were reviewed line-by-line