# Architecture Review Template (Lightweight)

## Summary
What is being built and why?

## Architecture Fit
- Does it respect current architecture boundaries?
- Any new services/modules introduced? Why?

## Domain Boundaries
- What is the domain ownership?
- Any cross-domain coupling risks?

## Data Design
- Tables/entities affected:
- Constraints & integrity:
- Migration strategy:

## API / Contracts
- Endpoints/interfaces affected:
- Backward compatibility concerns:

## Security
- AuthN/AuthZ impact:
- Data privacy/PII:
- Secrets handling:

## Performance & Scale
- Read/write hot paths:
- Caching/queues (only if required):
- Failure modes:

## Observability
- Logs:
- Metrics:
- Alerts:

## Risks & Mitigations
- Risk 1:
- Risk 2:

## Decision
- Approved / Approved with changes / Blocked
- Required changes (if any):