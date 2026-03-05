# Governance & Guardrails

## Architecture boundaries
- Presentation layer must not contain domain business rules
- Domain logic must be centralized and testable
- Data access is isolated behind repositories/queries
- AI orchestration must not bypass authorization or data isolation

## Reuse-first ladder
1) Find existing
2) Reuse
3) Extend
4) Refactor
5) Create new (only if needed)

## AI safety
- Suggestion-first outputs
- Human confirmation for writes
- Cite sources when retrieval is used
- Log decisions and changes