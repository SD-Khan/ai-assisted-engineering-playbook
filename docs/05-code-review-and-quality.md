# Code Review & Quality

AI-generated code must be reviewed with the same discipline as human-written code.

In practice, AI output introduces specific risks:
- over-engineering
- subtle edge case failures
- inconsistent patterns across the codebase
- “looks right” but violates architecture rules

---

## Review gates (minimum)

- architecture alignment
- correctness and validation
- error handling
- security posture
- test coverage
- observability
- maintainability and reuse

---

## AI-specific checks

- Is this solution simpler than necessary? (remove extra abstraction)
- Did AI introduce new dependencies? (block unless approved)
- Does it follow repo conventions and patterns?
- Are edge cases and failure states handled?
- Are tests actually verifying the right behavior?

---

## Quality enforcement approach

- keep tasks small
- require tests per meaningful change
- require verification steps
- prefer reuse-first over duplication
- record deviations consciously (not accidentally)